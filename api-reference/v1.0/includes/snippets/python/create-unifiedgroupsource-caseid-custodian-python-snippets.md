---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = UnifiedGroupSource(
	group = Group(
		mail = "SOCTeam@M365x809305.onmicrosoft.com",
	),
	included_sources = SourceType.Mailbox | SourceType.Site,
)

result = await graph_client.security.cases.ediscovery_cases.by_ediscovery_case_id('ediscoveryCase-id').custodians.by_ediscovery_custodian_id('ediscoveryCustodian-id').unified_group_sources.post(request_body)


```