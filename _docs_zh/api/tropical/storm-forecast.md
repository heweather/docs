---
title: 台风预报
tag: api
data: tropical
version: v7
description: 和风天气台风预报API接口提供全球主要海洋流域的热带低气压（台风）的预报信息，包括台风预测位置、等级、气压、风力、速度。
ref: 3-api-storm-forecast
---

台风预报API提供全球主要海洋流域的热带低气压（台风）的预报信息，包括台风预测位置、等级、气压、风力、速度。

> 如果查询的台风已经结束，则返回的数据为空，建议先通过[台风列表接口](/docs/api/tropical/storm-list/)获取台风的状态

### 请求URL

{% include api-url.html %}

### 请求参数

请求参数包括必选和可选参数，如不填写可选参数将使用其默认值，参数之间使用`&`进行分隔。

{% include params.html p="stormid key" %}

### 返回数据

{% include api-snippet.html %}

{% include api-response.html group="storm" type="forecast" prefix="forecast"  %}


## 台风等级

GBT 19201-2006

| 热带气旋等级        | 底层中心附近最大平均风速(m/s) | 底层中心附近最大风力(级) |
| ------------------- | ----------------------------- | ------------------------ |
| 热带气压（TD）      | 10.8-17.1                     | 6-7                      |
| 热带风暴（TS）      | 17.2-24.4                     | 8-9                      |
| 强热带风暴（STS）   | 24.5-32.6                     | 10-11                    |
| 台风（TY）          | 32.7-41.4                     | 12-13                    |
| 强台风（STY）       | 41.5-50.9                     | 14-15                    |
| 超强台风（SuperTY） | ≥51.0                         | 16或以上                 |
