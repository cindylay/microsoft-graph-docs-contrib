---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)


await graph_client.me.online_meetings.by_online_meeting_id('onlineMeeting-id').registration.registrants.by_meeting_registrant_base_id('meetingRegistrantBase-id').delete()


```