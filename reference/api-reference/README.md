# API Reference

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

{% content-ref url="custom_data.md" %}
[custom\_data.md](custom\_data.md)
{% endcontent-ref %}

Data sent via this API will appear in **Costs Overview** and **Unit Metrics Lab** on Cloudthread's platform.

## Event Overlay Ingestion

Cloudthread provides the ability to send webhook Events that can be overlayed on top of your Cost Views and Unit Metrics.

{% content-ref url="events.md" %}
[events.md](events.md)
{% endcontent-ref %}

Data sent via this API will appear in **Costs Overview** and **Unit Metrics Lab** on Cloudthread's platform.

## Tag Catalog Fetch

Cloudthread provides the ability to fetch a Tag Catalog entry via catalog key.

{% content-ref url="tag_catalog.md" %}
[tag\_catalog.md](tag\_catalog.md)
{% endcontent-ref %}

## Cost View and Unit Metric Data Fetch

Cloudthread provides the ability to fetch a Cost View and Unit Metric data.

{% content-ref url="metrics.md" %}
[metrics.md](metrics.md)
{% endcontent-ref %}

## Users and Teams setup

API can be used to set up Users and Teams.

{% content-ref url="users.md" %}
[users.md](users.md)
{% endcontent-ref %}

{% content-ref url="teams.md" %}
[teams.md](teams.md)
{% endcontent-ref %}
