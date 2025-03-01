---
title: "riskUserActivity resource type"
description: author
author: "tracyshi"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# riskUserActivity resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

## Properties

| Property       | Type    |Description|
|:---------------|:--------|:----------|
| detail     | riskDetail  | The possible values are `none`, `adminGeneratedTemporaryPassword`, `userPerformedSecuredPasswordChange`, `userPerformedSecuredPasswordReset`, `adminConfirmedSigninSafe`, `aiConfirmedSigninSafe`, `userPassedMFADrivenByRiskBasedPolicy`, `adminDismissedAllRiskForUser`, `adminConfirmedSigninCompromised`, `hidden`, `adminConfirmedUserCompromised`, `unknownFutureValue`.  |
| riskEventType | String collection | The type of risk event detected. The possible values are: `anonymizedIPAddress`, `investigationsThreatIntelligence`, `investigationsThreatIntelligenceSigninLinked`,`leakedCredentials`, `maliciousIPAddress`, `maliciousIPAddressValidCredentialsBlockedIP`, `malwareInfectedIPAddress`, `mcasImpossibleTravel`, `mcasSuspiciousInboxManipulationRules`, `suspiciousAPITraffic`, `suspiciousIPAddress`,   `unfamiliarFeatures`, `unlikelyTravel`. For more information about these values, see [riskDetection: riskEventType](../resources/riskdetection.md#riskeventtype-values). |
| eventTypes (deprecated) | riskEventType collection |List of risk event types. Deprecated. Use **riskEventType** instead. |

## JSON representation

<!-- {
  "blockType": "resource",
  "optionalProperties": [ ],
  "@odata.type": "microsoft.graph.riskUserActivity"
}-->
```json
{
    "eventTypes": ["String"],
    "riskEventType": ["String"],
    "detail": "String"
}
```
<!--
{
  "type": "#page.annotation",
  "description": "",
  "keywords": "",
  "section": "",
  "tocPath": "",
  "suppressions": []
}
-->


