---
title: Weather Warning
tag: api
data: warning
version: v7
description: QWeather Weather Warning API for getting real-time local severe weather warning.
ref: 1-api-weather-warning
---

Weather Warning API for getting real-time local severe weather warning.

> Only China data is supported

### Request URL

{% include api-url.html flag="weather-warning" %}

### Request Parameters

All parameters are separated by `&`. If no optional parameters are set, the default value will be used.

{% include params.html p="key location lang-zhen" %}

### Response

> If there is no warning information in the queried location, the `warning` field is empty.
{:.bqwarning}

{% include api-snippet.html %}

{% include api-response.html group="warning" type="warning" prefix="warning" %}
