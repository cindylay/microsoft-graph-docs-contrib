---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedList<SearchRequest> requestsList = new LinkedList<SearchRequest>();
SearchRequest requests = new SearchRequest();
LinkedList<EntityType> entityTypesList = new LinkedList<EntityType>();
entityTypesList.add(EntityType.LIST_ITEM);
requests.entityTypes = entityTypesList;
requests.region = "US";
SearchQuery query = new SearchQuery();
query.queryString = "contoso";
query.queryTemplate = "{searchTerms} CreatedBy:Bob";
requests.query = query;
requests.from = 0;
requests.size = 25;

requestsList.add(requests);

graphClient.search()
	.query(SearchEntityQueryParameterSet
		.newBuilder()
		.withRequests(requestsList)
		.build())
	.buildRequest()
	.post();

```