---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = CalendarPermission(
	role = CalendarRoleType.Write,
)

result = await graph_client.users.by_user_id('user-id').calendars.by_calendar_id('calendar-id').calendar_permissions.by_calendar_permission_id('calendarPermission-id').patch(request_body)


```