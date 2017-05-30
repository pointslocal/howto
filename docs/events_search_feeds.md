# Creating Feeds From Searches
> Any Pointslocal search endpoint can be represented as an RSS feed.  This permits social sharing and syndication of granular topics and time frames.  This tutorial will show how to construct these feeds from existing searches or generate them automatically from the version 3.0 admin.

_Note: feed generation is not available in versions prior to 3.0_

## Creating General Feeds From Front-End
> To create a feed based on specific criteria, the easiest method is to start with a search on your user-facing site.  *Use Case:* You wish to produce an RSS feed of "live music" events for "this weekend."

1. Go to your events home site, www.yoursite.com/home
2. Under the **What** dropdown in the search box, select _Live Music_
3. Under the **When** dropdown in the search box, select _This Weekend_
4. Click Apply or Go to start the search
5. Note the URL.  It should look something like this www.yoursite.com/events?neighborhoods=&categories=YY&range=this-weekend, where the categories represent the selected category
6. Change the text starting with /events to be /events/feed/rss.  In this case, the URL would become: www.yoursite.com/events/feeds/rss?neighborhoods=&categories=YY&range=this-weekend
7. This represents an RSS feed that will be always return the live music events for the next weekend

![Searching What](https://pointslocal.github.io/howto/images/events_search_what.png)

![Searching When](https://pointslocal.github.io/howto/images/events_search_when.png)


Any search can be transformed in this manner by changing /events to /events/feed/rss.  Here are some common search parameters:

* categories=XX,YY,ZZ where XX,YY,ZZ represents a comma-separated list of category IDs
* neighborhoods=XX,YY,ZZ where XX,YY,ZZ represents a comma-separated list of neighborhood IDs
* venue=XX where XX represents a venue ID
* range=Text where Text represents a valid relative date like "today" "tomorrow" "this-weekend" "this-month" "next-week" or "next-month"
* tag=Text where Text represents an arbitrary tag in the admin
* venue_guid=XX where XX represents the venue's GUID (from the admin)

_Note: any search can exclude fuzzy or near matches by applying the &exact=1 parameter.  This is most useful in category or date-based searches_

