---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = ReferenceCreate(
	odata_id = "https://graph.microsoft.com/beta/policies/appManagementPolicies/{id}",
)

await graph_client.applications.by_application_id('application-id').app_management_policies.ref.post(request_body)


```