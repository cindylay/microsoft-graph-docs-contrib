---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = UnifiedRoleManagementPolicyEnablementRule(
	odata_type = "#microsoft.graph.unifiedRoleManagementPolicyEnablementRule",
	id = "Enablement_EndUser_Assignment",
	enabled_rules = [
		"Justification",
		"MultiFactorAuthentication",
		"Ticketing",
	],
	target = UnifiedRoleManagementPolicyRuleTarget(
		odata_type = "microsoft.graph.unifiedRoleManagementPolicyRuleTarget",
		caller = "EndUser",
		operations = [
			UnifiedRoleManagementPolicyRuleTargetOperations.All,
		],
		level = "Assignment",
		inheritable_settings = [
		],
		enforced_settings = [
		],
	),
)

result = await graph_client.policies.role_management_policies.by_unified_role_management_policy_id('unifiedRoleManagementPolicy-id').rules.by_unified_role_management_policy_rule_id('unifiedRoleManagementPolicyRule-id').patch(request_body)


```