---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php


$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new BookingService();
$requestBody->setOdataType('#microsoft.graph.bookingService');
$requestBody->setDefaultDuration(new \DateInterval('PT30M'));

$result = $graphServiceClient->bookingBusinesses()->byBookingBusinessId('bookingBusiness-id')->services()->byBookingServiceId('bookingService-id')->patch($requestBody)->wait();

```