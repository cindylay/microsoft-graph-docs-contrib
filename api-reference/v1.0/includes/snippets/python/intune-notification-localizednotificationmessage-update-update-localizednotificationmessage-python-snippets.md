---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = LocalizedNotificationMessage(
	odata_type = "#microsoft.graph.localizedNotificationMessage",
	locale = "Locale value",
	subject = "Subject value",
	message_template = "Message Template value",
	is_default = True,
)

result = await graph_client.device_management.notification_message_templates.by_notification_message_template_id('notificationMessageTemplate-id').localized_notification_messages.by_localized_notification_message_id('localizedNotificationMessage-id').patch(request_body)


```