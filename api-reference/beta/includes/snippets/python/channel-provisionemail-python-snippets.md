---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)


result = await graph_client.teams.by_team_id('team-id').channels.by_channel_id('channel-id').provision_email.post()


```