---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = EnrollAssetsPostRequestBody(
	update_category = UpdateCategory.Feature,
	assets = [
		AzureADDevice(
			odata_type = "#microsoft.graph.windowsUpdates.azureADDevice",
			id = "String (identifier)",
		),
	],
)

await graph_client.admin.windows.updates.updatable_assets.microsoft_graph_windows_updates_enroll_assets.post(request_body)


```