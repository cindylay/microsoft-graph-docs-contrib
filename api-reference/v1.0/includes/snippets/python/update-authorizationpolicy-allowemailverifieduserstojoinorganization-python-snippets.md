---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = AuthorizationPolicy(
	allow_email_verified_users_to_join_organization = False,
)

result = await graph_client.policies.authorization_policy.patch(request_body)


```