# Quick Start

Cloudthread provides a powerful and flexible REST Developer API to help you get the most out of your data.

This page shows how to use the API, and what features are currently available.

## Basic setup

Cloudthread's Developer API lives at

`https://api.cloudthread.io`

Cloudthread requires an API Token to process incoming developer API requests. Admin's have the ability to generate API Tokens on the Cloudthread platform within the **Settings** tab.

This API Token should be included in the headers for all Developer API requests as follows:

`x-api-key: {API_TOKEN}`

Any request without a valid token will be rejected.

## Custom Data Ingestion

Cloudthread provides the ability to send custom data to our systems that can then be used in your Cost Views and Unit Metrics.

In order to send custom data, you must provision a **Custom Data - Data Stream Token** on the Cloudthread platform within the **Settings** tab.

{% content-ref url="reference/api-reference/custom_data.md" %}
[custom_data.md](reference/api-reference/custom_data.md)
{% endcontent-ref %}

Data sent via this API will appear in **Costs Overview** and **Unit Metrics Lab** on Cloudthread's platform.

## Event Overlay Ingestion

Cloudthread provides the ability to send webhook Events that can be overlayed on top of your Cost Views and Unit Metrics.

{% content-ref url="reference/api-reference/events.md" %}
[events.md](reference/api-reference/events.md)
{% endcontent-ref %}

Data sent via this API will appear in **Costs Overview** and **Unit Metrics Lab** on Cloudthread's platform.

## Tag Catalog Fetch

Cloudthread provides the ability to fetch a Tag Catalog entry via catalog key.

{% content-ref url="reference/api-reference/tag_catalog.md" %}
[tag_catalog.md](reference/api-reference/tag_catalog.md)
{% endcontent-ref %}


## Cost View and Unit Metric Data Fetch

Cloudthread provides the ability to fetch a Cost View and Unit Metric data.

{% content-ref url="reference/api-reference/metrics.md" %}
[metrics.md](reference/api-reference/metrics.md)
{% endcontent-ref %}
