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

Cloudthread provides the ability to send data to our systems that can then be used on the platform.

In order to send custom data, you must provision a **Custom Data - Data Stream Token** on the Cloudthread platform within the **Settings** tab.

{% content-ref url="reference/api-reference/pets.md" %}
[pets.md](reference/api-reference/pets.md)
{% endcontent-ref %}

Data sent via this API will appear in the **Unit Metrics Lab** on Cloudthread's platform.

## Event Overlay Ingestion

Cloudthread can process webhook events that can be overlayed on top of your cost data and unit metrics.

{% content-ref url="reference/api-reference/users.md" %}
[users.md](reference/api-reference/users.md)
{% endcontent-ref %}

Data sent via this API will appear in **Costs Overview** and **Unit Metrics Lab** on Cloudthread's platform.

## Tag Catalog Fetch

Cloudthread provides the ability to fetch a tag catalog via catalog key.

{% content-ref url="reference/api-reference/users.md" %}
[users.md](reference/api-reference/users.md)
{% endcontent-ref %}


## Data Querying API

{% hint style="info" %}
**COMING SOON**

Please contact [support@cloudthread.io](mailto:support@cloudthread.io) for more information about this feature**.**
{% endhint %}
