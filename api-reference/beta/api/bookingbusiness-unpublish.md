---
title: "bookingBusiness: unpublish"
description: "Make the scheduling page of this business not available to external customers."
ms.localizationpriority: medium
author: "arvindmicrosoft"
ms.prod: "bookings"
doc_type: apiPageType
---

# bookingBusiness: unpublish

Namespace: microsoft.graph

 [!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Make the scheduling page of this business not available to external customers.

Set the **isPublished** property to false, and **publicUrl** property to null.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "bookingbusiness_unpublish" } -->
[!INCLUDE [permissions-table](../includes/permissions/bookingbusiness-unpublish-permissions.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /solutions/bookingbusinesses/{id}/unpublish

```
## Request headers
| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer {code}|

## Request body

## Response
If successful, this method returns `204 No content` response code. It doesn't return anything in the response body.

## Example
The following is an example of how to call this API.
##### Request
The following example shows a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "bookingbusiness_unpublish",
  "sampleKeys": ["contosolunchdelivery@contoso.onmicrosoft.com"]
}-->
```http
POST https://graph.microsoft.com/beta/solutions/bookingbusinesses/contosolunchdelivery@contoso.onmicrosoft.com/unpublish
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/bookingbusiness-unpublish-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/bookingbusiness-unpublish-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/bookingbusiness-unpublish-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/bookingbusiness-unpublish-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/bookingbusiness-unpublish-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/bookingbusiness-unpublish-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/bookingbusiness-unpublish-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/bookingbusiness-unpublish-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

##### Response
The following example shows the response.
<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 204 No content
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "bookingBusiness: unpublish",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->


