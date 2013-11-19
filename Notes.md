Drink With Friends Development Notes
====================================

November 18th, 2013
-------------------

I think we should split the interactions into persistent
and non-persistent interactions:

Non-continuous data will be "Who are you drinking with tonight?",
"What beers do your friends tonight prefer drinking?", and 
(the question our app answers) "Where are you drinking tonight?"

Persistent data will be, "That friend F_1 likes beer B." and "That friend
F_2 frequents pub P."

The persistent data should be cached and brought back in each session.

The way this affects implementation is that when our user attributes
liking a beer or frequenting a bar to a friend or serving a beer to 
a bar, that should persist. But the friends drinking tonight should
be non-persistent and selected each time.

So, specifically, the user selects 5 of their friends from the
Address Book. Say the user has drank with 3 of them in the past and
found their preferences, these should be cached and available. For
the 2 new friends, new database entries should be entered and the
user queried for their presumed/guessed/generated beer preference.
Upon the list of local bars, the user should be queried for which
of their friends frequent any of the available bars (if any) where
a bar a friend frequents will be taken as a feature that makes that
bar more preferable than one which is equivalent in all regards
except for not being frequented by that friend.

### Persistent Interactions

-   Classifying a friend as liking a beer.
-   Classifying a friend as frequenting a bar.
-   Classifying a bar as serving a beer.

### Non-Persistent Interaction

-   Selecting a friend to go drinking with.
-   Selecting a bar to go drinking at.

### On Shortest Paths

We'll have to find the least expensive order or getting friends.
Then, from that friend's house, the bars closer are more desirable.

Path route can be gotten from MapKit or Google Maps.

http://stackoverflow.com/questions/12002179/finding-path-route-between-two-points-on-mapkit-in-iphone
