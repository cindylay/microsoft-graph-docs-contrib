---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)


request_configuration = DeltaRequestBuilder.DeltaRequestBuilderGetRequestConfiguration()
request_configuration.headers.add("Prefer", "odata.maxpagesize=2")


result = await graph_client.me.contact_folders.delta.get(request_configuration = request_configuration)


```