Filters are usuable in Calendar views in the Graph where in EWS you could never use a Search Filter when using Calendar View.
If your using an Extended property as a Filter you must first expand it before using it in a Filter
eg (Simple sample that filters using the Extended property for the Subject)

```
https://graph.microsoft.com/v1.0/me/calendar/calendarView?
startDateTime=2022-09-01T19:00:00Z&endDateTime=2022-09-10T19:00:00Z&$select=subject&
$expand=singleValueExtendedProperties($filter=id eq 'String 0x0037')&
$filter=singleValueExtendedProperties/any(ep: ep/id eq 'String 0x0037' and ep/value eq 'Cloud and Mobile Working Group')
```

