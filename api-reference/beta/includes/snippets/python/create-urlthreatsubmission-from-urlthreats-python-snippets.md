---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = UrlThreatSubmission(
	odata_type = "#microsoft.graph.urlThreatSubmission",
	category = SubmissionCategory.Phishing,
	web_url = "http://phishing.contoso.com",
)

result = await graph_client.security.threat_submission.url_threats.post(request_body)


```