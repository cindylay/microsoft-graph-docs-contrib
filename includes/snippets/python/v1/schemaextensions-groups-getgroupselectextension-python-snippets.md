---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

query_params = GroupsRequestBuilder.GroupsRequestBuilderGetQueryParameters(
		filter = "bellowscollege_courses/courseId eq '123'",
		select = ["displayName","id","description","bellowscollege_courses"],
)

request_configuration = GroupsRequestBuilder.GroupsRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.groups.get(request_configuration = request_configuration)


```