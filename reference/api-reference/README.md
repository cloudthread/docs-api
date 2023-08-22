# API Reference

Cloudthread provides a powerful and flexible **REST Developer API** to help you get the most out of your data.

These docs show how to use the API, and what features are currently available.

{% hint style="info" %}
**Good to know:** All the API methods referenced in the docs are synced to a Swagger file URL (**OpenAPI v3**) and are kept up to date **automatically** with changes to the API.
{% endhint %}

## Basic setup

Cloudthread's **Developer API** lives at:

{% embed url="https://api.cloudthread.io" fullWidth="false" %}

{% hint style="warning" %}
Cloudthread requires an **API Token** to process incoming developer API requests.&#x20;

Admin's have the ability to generate API Tokens on the Cloudthread platform within the [Settings](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/settings "mention") tab.
{% endhint %}

This API Token should be included in the headers for all Developer API requests as follows:

`x-api-key: {API_TOKEN}`

{% hint style="danger" %}
Any request without a valid token will be **rejected**.
{% endhint %}

## Custom Data ingestion

Cloudthread provides the ability to send custom data to our systems that can then be used in your Cost Views and Unit Metrics.

In order to send custom data, you must provision a **Custom Data - Data Stream Token** on the Cloudthread platform within the [Settings](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/settings "mention") tab.

{% content-ref url="custom_data.md" %}
[custom\_data.md](custom\_data.md)
{% endcontent-ref %}

Data sent via this API will appear in [Costs Overview](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/costs-overview "mention") and [Unit Metrics Lab](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/unit-metrics-lab "mention") on Cloudthread's platform.

## Event Overlay ingestion

Cloudthread provides the ability to send **webhook** **events** that can be overlayed on top of your [Cost Views](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/key-concepts/cost-view "mention") and [Unit Metrics](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/key-concepts/unit-metric "mention"). See [Events Overlay](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/key-concepts/events-overlay "mention") for more details.

{% content-ref url="events.md" %}
[events.md](events.md)
{% endcontent-ref %}

Data sent via this API will appear in [Costs Overview](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/costs-overview "mention") and [Unit Metrics Lab](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/unit-metrics-lab "mention") on Cloudthread's platform.

## Tag Catalog fetch

Cloudthread provides the ability to fetch a [Tags Catalog](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/tag-assistant/tag-catalogs "mention") entry via catalog key.

{% content-ref url="tag_catalog.md" %}
[tag\_catalog.md](tag\_catalog.md)
{% endcontent-ref %}

## Cost View and Unit Metric Data fetch

Cloudthread provides the ability to fetch [Cost Views](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/key-concepts/cost-view "mention") and [Unit Metrics](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/key-concepts/unit-metric "mention") data.

{% content-ref url="metrics.md" %}
[metrics.md](metrics.md)
{% endcontent-ref %}

## Users and Teams setup

API can be used to set up and change **Users** (see [User Management](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/settings/account-and-team-management "mention")) and [Teams](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/settings/teams "mention").

{% content-ref url="users.md" %}
[users.md](users.md)
{% endcontent-ref %}

{% content-ref url="teams.md" %}
[teams.md](teams.md)
{% endcontent-ref %}

## Savings Hub manipulation

API to retrive and setup [Savings Opportunities](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-savings/key-concepts/optimization-opportunities "mention") and [Savings Threads](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-savings/key-concepts/savings-threads "mention").

{% content-ref url="savings-hub/" %}
[savings-hub](savings-hub/)
{% endcontent-ref %}
