---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = ReferenceUpdate(
	odata_id = "https://graph.microsoft.com/beta/identity/apiConnectors/{id}",
)

await graph_client.identity.b2x_user_flows.by_b2x_identity_user_flow_id('b2xIdentityUserFlow-id').api_connector_configuration.post_attribute_collection.ref.put(request_body)


```