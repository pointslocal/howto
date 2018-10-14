# Using Event Templates For Search
> Event templates provide a way to create repeatable events searches. They're primarily used for reverse publishing, but can also be used for any type of advanced search that is relative and repeatable. 

## Some examples:
* Search Arts and Music categories starting next Thursday to two Thursdays.
* Search events downtown this weekend, submitted by users
* Search published events that are Editor's Picks or tagged Featured

## Creating Event Templates
Creation of event templates is a somewhat advanced topic, and requires knowledge of both the API and JSON format. The API can be found here: https://pointslocal.readthedocs.io/en/latest/api_events_events/

Under the top-left "Hamburger" navigation, click the section titled Exports. From here you can create a New Export. On this page there are three sections:

1. Template - this defines how the templatewill work with reverse publishing
2. Preprocessing - this allows modifying the data to match styles for reverse publishing
3. Configuration - this is how the data is gathered. It can look something like the following:

```json
{
  "api": {
    "endpoint": "events",
    "count": "100",
    "start": "this Friday",
    "end": "+2 Fridays",
    "recurrences": 1
  },
  "filename": "myexport-{{formatted-date}}.txt",
  "outputs": [

  ],
  "groupBy": [
    "date"
  ],
  "orderBy": [],
  "schedule": [

  ]
}
```

You can also request templates be configured by emailing support@pointslocal.com directly.

## Using Event Templates for Search
Once a template is created it is also available for search in the admin. To do so, simply navigate to the top level Events link. 

![Search](https://pointslocal.github.io/howto/images/events_templates_search.png)

Then click the search icon to open the search options. From here, use the "Template" section to select the configuration you would like to search on. Finally, click Search.

![Search](https://pointslocal.github.io/howto/images/events_templates_search2.png)

Some search options can override the template. This is useful if you have a pre-baked search but want to override the dates, for example. If you had an Entertainment template that ran Thursday to Sunday but wanted to search for the same events for two weeks, you could select the Entertainment template but supply your own date search.

When selecting a template-based search, the number of results will be higher than a traditional page, but is still truncated. You may see several pages of results.

If - instead of just searching events - you wish to export the results, select all or some of the results. Once more than one event is selected the Export button at the bottom of the screen will activate. You can then choose the template you wish and the reverse publishing file will be generated. Depending on that export's configuration, the results will come to screen, exported to your CMS, emailed to certain users or any combination of the above.

![Search](https://pointslocal.github.io/howto/images/events_templates_search3.png)