---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = MailFolder(
	display_name = "Clutter",
	is_hidden = True,
)

result = await graph_client.me.mail_folders.post(request_body)


```