---
title: "riskDetection resource type"
description: "Represents all risk detections in AzureAD tenants."
author: "tracyshi"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---
# riskDetection resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents information about a detected risk in a Microsoft Entra tenant. 

Microsoft Entra ID Protection continually evaluates [user risks](riskyuser.md) and app or user [sign-in](signin.md) risks based on various signals and machine learning. This API provides programmatic access to all risk detections in your Microsoft Entra environment.

For more information about risk detection, see [Microsoft Entra ID Protection](/entra/id-protection/overview-identity-protection) and [What are risk detections?](/entra/id-protection/concept-identity-protection-risks)

>[!NOTE]
> The availability of risk detection data is governed by the [Microsoft Entra data retention policies](/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).

## Methods

| Method   | Return Type|Description|
|:---------------|:--------|:----------|
|[List riskDetection](../api/riskdetection-list.md) | [riskDetection](riskdetection.md) collection|List risk detections and their properties.|
|[Get riskDetection](../api/riskdetection-get.md) | [riskDetection](riskdetection.md)|Get a specific risky detection and its properties.|

## Properties

| Property   | Type|Description|
|:---------------|:--------|:----------|
|activity|activityType|Indicates the activity type the detected risk is linked to. The possible values are `signin`, `user`, `unknownFutureValue`. |
|activityDateTime|DateTimeOffset|Date and time that the risky activity occurred. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|additionalInfo|string|Additional information associated with the risk detection in JSON format. |
|correlationId|string|Correlation ID of the sign-in associated with the risk detection. This property is null if the risk detection is not associated with a sign-in. |
|detectedDateTime|DateTimeOffset|Date and time that the risk was detected. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z` |
|detectionTimingType|riskDetectionTimingType|Timing of the detected risk (real-time/offline). The possible values are `notDefined`, `realtime`, `nearRealtime`, `offline`, `unknownFutureValue`. |
|id|string|Unique ID of the risk detection. |
|ipAddress|string|Provides the IP address of the client from where the risk occurred. |
|lastUpdatedDateTime|DateTimeOffset|Date and time that the risk detection was last updated. |
|location|[signInLocation](signinlocation.md)|Location of the sign-in. |
|requestId|string|Request ID of the sign-in associated with the risk detection. This property is null if the risk detection is not associated with a sign-in.|
|riskEventType|String|The type of risk event detected. The possible values are `adminConfirmedUserCompromised`, `anomalousUserActivity`, `anonymizedIPAddress`, `generic`, `investigationsThreatIntelligence`, `investigationsThreatIntelligenceSigninLinked`,`leakedCredentials`, `maliciousIPAddress`, `maliciousIPAddressValidCredentialsBlockedIP`, `malwareInfectedIPAddress`, `mcasImpossibleTravel`, `mcasSuspiciousInboxManipulationRules`, `suspiciousAPITraffic`, `suspiciousIPAddress`,   `unfamiliarFeatures`, `unlikelyTravel`, `userReportedSuspiciousActivity`. <br/> For more information about each value, see [riskEventType values](#riskeventtype-values).|
|riskDetail|riskDetail|Details of the detected risk. The possible values are: `none`, `adminGeneratedTemporaryPassword`, `userPerformedSecuredPasswordChange`, `userPerformedSecuredPasswordReset`, `adminConfirmedSigninSafe`, `aiConfirmedSigninSafe`, `userPassedMFADrivenByRiskBasedPolicy`, `adminDismissedAllRiskForUser`, `adminConfirmedSigninCompromised`, `hidden`, `adminConfirmedUserCompromised`, `unknownFutureValue`, `adminConfirmedServicePrincipalCompromised`, `adminDismissedAllRiskForServicePrincipal`, `m365DAdminDismissedDetection`. Note that you must use the `Prefer: include - unknown -enum-members` request header to get the following value(s) in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `adminConfirmedServicePrincipalCompromised` , `adminDismissedAllRiskForServicePrincipal` , `m365DAdminDismissedDetection`. <br/><br />**Note:** Details for this property are only available for Microsoft Entra ID P2 customers. P1 customers will be returned `hidden`.|
|riskLevel|riskLevel|Level of the detected risk. The possible values are `low`, `medium`, `high`, `hidden`, `none`, `unknownFutureValue`. <br />**Note:** Details for this property are only available for Microsoft Entra ID P2 customers. P1 customers will be returned `hidden`.|
|riskState|riskState|The state of a detected risky user or sign-in. The possible values are `none`, `confirmedSafe`, `remediated`, `dismissed`, `atRisk`, `confirmedCompromised`, and `unknownFutureValue`. |
|source|string|Source of the risk detection. For example, `activeDirectory`. |
|tokenIssuerType|tokenIssuerType|Indicates the type of token issuer for the detected sign-in risk. The possible values are `AzureAD`, `ADFederationServices`, and `unknownFutureValue`.|
|userId|string|Unique ID of the user.  The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|userDisplayName|string|Name of the user. |
|userPrincipalName|string|The user principal name (UPN) of the user. |
|riskType (deprecated)|riskEventType|List of risk event types.<br />**Note:** This property is deprecated. Use **riskEventType** instead. |

### riskEventType values

| Member | Description |
|--|--|
| adminConfirmedUserCompromised | Indicates that an administrator has [confirmed the user is compromised](../api/riskyusers-confirmcompromised.md). |
| anomalousUserActivity | Indicates a suspicious pattern of behavior for a user that is anomalous to past behavioral patterns |
| anonymizedIPAddress | Indicates sign-ins from an anonymous IP address, for example, using an anonymous browser or VPN. |
| generic | Indicates that the user was not enabled for Identity Protection. |
| investigationsThreatIntelligence | Indicates a sign-in activity that is unusual for the given user or is consistent with known attack patterns based on Microsoft's internal and external threat intelligence sources. |
| investigationsThreatIntelligenceSigninLinked | Identifies activity that is unusual with known attack patterns based on threat intelligence |
| leakedCredentials | Indicates that the user's valid credentials have been leaked. This sharing is typically done by posting publicly on the dark web, paste sites, or by trading and selling the credentials on the black market. When the Microsoft leaked credentials service acquires user credentials from the dark web, paste sites, or other sources, they are checked against Microsoft Entra users' current valid credentials to find valid matches. |
| maliciousIPAddress | Indicates sign-ins from IP addresses known to be malicious. Deprecated and no longer generated for new detections. |
| maliciousIPAddressValidCredentialsBlockedIP | Indicates that sign-in was made with valid credentials from a malicious IP address. |
| malwareInfectedIPAddress | Indicates sign-ins from IP addresses infected with malware |
| mcasImpossibleTravel | Discovered by Microsoft Defender for Cloud Apps (MDCA). Identifies two user activities (a single or multiple sessions) originating from geographically distant locations within a time period shorter than the time it would have taken the user to travel from the first location to the second, indicating that a different user is using the same credentials. |
| mcasSuspiciousInboxManipulationRules | Discovered by Microsoft Defender for Cloud Apps (MDCA). Identifies suspicious email forwarding rules, for example, if a user created an inbox rule that forwards a copy of all emails to an external address.|
| suspiciousAPITraffic | Indicates that a user's API traffic is suspicious based on the user's observed baseline activity. Possible types of suspicious activity are logged in the **additionalInfo** property and include the following values: <br/> <li> `AnomalousDirectoryEnumeration` which indicates that the user has made anomalous calls to the directory  <li> `AnomalousAPICallsExchange` which indicates that the user has made anomalous calls to an Exchange resource <li> `AnomalousAPICallsOneDrive` which indicates that the user has made anomalous calls to a OneDrive resource. <br/><br/>For each type of activity, the amount of variation from the user's baseline behavior can be `NoVolumeObserved` if the user has no observed baseline behavior, `FiveTimesGreater` if the activity is up to five times greater than the observed baseline, `HundredTimesGreater` if the activity is up to 100 times greater than the observed baseline, and `ThousandTimesGreater` if the activity is up to 1000 times greater than the observed baseline. |
| suspiciousIPAddress | Identifies logins from IP addresses that are known to be malicious at the time of the sign in. |
| unfamiliarFeatures | Indicates sign-ins with characteristics that deviate from past sign-in properties. |
| unlikelyTravel | Identifies two sign-ins originating from geographically distant locations, where at least one of the locations may also be atypical for the user, given past behavior.  |
| userReportedSuspiciousActivity | Indicates that a user reported a voice or phone app notification MFA prompt as suspicious, signalling that the user's credentials are potentially compromised. |


## JSON representation

The following JSON representation shows the resource type.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.riskDetection"
}-->

```json
{
 "id": "string",
    "requestId": "string",
    "correlationId": "string",
    "riskType": {"@odata.type": "microsoft.graph.riskEventType"},
    "riskState": {"@odata.type": "microsoft.graph.riskState"},
    "riskLevel": {"@odata.type": "microsoft.graph.riskLevel"},
    "riskDetail": {"@odata.type": "microsoft.graph.riskDetail"},
    "source": "string",
    "detectionTimingType": {"@odata.type": "microsoft.graph.riskDetectionTimingType"},
    "activity": {"@odata.type": "microsoft.graph.riskUserActivity"},
    "tokenIssuerType": {"@odata.type": "microsoft.graph.tokenIssuerType"},
    "ipAddress": "string",
    "location": {"@odata.type": "microsoft.graph.signInLocation"},
    "activityDateTime": "string (timestamp)",
    "detectedDateTime": "string (timestamp)",
    "lastUpdatedDateTime": "string (timestamp)",
    "userId": "string",
    "userDisplayName": "string",
    "userPrincipalName": "string",
    "additionalInfo": "string"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "riskDetections resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
