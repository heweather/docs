---
title: City Lookup
tag: api
data: geo
version: v2
description: QWeather city look up API interface GeoAPI provides global geographic location, global city search services, supports longitude and latitude coordinate reverse check, multi-language, fuzzy search and other functions.
ref: 1-api-city-lookup
---

Weather data is based on geographic location, so you need to know the specific location information before you can get the weather. 

With the GeoAPI - City Lookup, you can get the basic information of the city, including the Location ID of the city (you need this ID to get the weather), multilingual name, latitude and longitude, time zone, altitude, rank, administrative, etc.

In addition, GeoAPI - City Lookup can also help you to implement fuzzy search in your APP, users only need to type 1 or 2 words to get results.

> GeoAPI is free for the first 50,000 calls per day for each account, more calls refer to [price](/en/help/buy#price)
{:.bqwarning}

### Request URL

{% include api-url.html flag="city-lookup" %}

### Request Parameters

All parameters are separated by `&`. If no optional parameters are set, the default value will be used.

{% include params.html p="location-geo" %}

> **Fuzzy search**, when the location passed as text, fuzzy search is supported, users can only enter a part of the city name to search, at least one Chinese character or 2 characters, and the results are sorted by correlation and [Rank](/en/docs/start/glossary/#rank). It is easy for developers or users to choose which city they need to see the weather. For example, `location=bei` will return some of the most relevant results to **bei**, including Beirut in Lebanon and Beijing in China

> **Duplicate name**, when the location is passed as text, cities with the same name may appear, such as Xi'an in Shaanxi Province, Xi'an District under Liaoyuan City in Jilin Province, and Xi'an District under Mudanjiang City in Heilongjiang Province. At this time, all results will be returned according to the [Rank](/en/docs/start/glossary/#rank). In this case, you can use the `adm` parameter to further determine the city or region that needs to be queried, for example, `location=Xi’an&adm=Heilongjiang`

{% include params.html p="key adm" %}

> If with `adm`, like `location=chaoyang&adm=beijing`, the returned results only include Chaoyang District in Beijing, not Chaoyang City in Liaoning Province
>
> If without `adm`, like `location=chaoyang`, the returned results include Chaoyang District in Beijing, Chaoyang City in Liaoning Province, and Chaoyang District in Changchun City

{% include params.html p="range number lang" %}

### Response

{% include api-snippet.html flag="city-lookup" %}

{% include api-response.html group="geo" type="location" prefix="location" update=0 fxlink=0 %}