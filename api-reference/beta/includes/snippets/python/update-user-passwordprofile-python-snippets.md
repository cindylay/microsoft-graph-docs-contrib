---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = User(
	password_profile = PasswordProfile(
		force_change_password_next_sign_in = True,
		password = "xWwvJ]6NMw+bWH-d",
	),
)

result = await graph_client.users.by_user_id('user-id').patch(request_body)


```