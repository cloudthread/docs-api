# Metric Fetch

## Cost View Fetch

Cloudthread provides the ability to query your [Cost Views](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/key-concepts/cost-view "mention").

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/cost/metric/{metric_id}" method="get" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

To query [Cost Views](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/key-concepts/cost-view "mention"), use the endpoint above and the following query parameters:

* Path (go after `/` in the URL)
  * `metric_id`: the ID of the Cost View you wish to query
* Query (go after `?` in the URL)
  * `start_date`: start date of the timeframe you wish to query – formatted as YYYY-MM-DD, required
  * `end_date`: inclusive end date of the timeframe you wish to query – formatted as YYYY-MM-DD
  * `cost_type`: OPTIONAL – specifies the cost type (Unblended, Public, etc.)
  * `amortization`: OPTIONAL – specifies if to include amortization
  * `exclude`: OPTIONAL – specifies if to exclude taxes, refunds, etc.
  * `granularity`: OPTIONAL – specifies the data granularity (hour, day, week, quarter, year)

{% hint style="info" %}
If the data pass **validation** a `200` status code.
{% endhint %}

## Unit Metric Fetch

Cloudthread provides the ability to query your [Unit Metrics](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/key-concepts/unit-metric "mention").

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/unit/metric/{metric_id}" method="get" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

To query [Unit Metrics](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/key-concepts/unit-metric "mention") use the endpoint above and the following query parameters:

* Path (go after `/` in the URL)
  * `metric_id`: the ID of the Unit Metric you wish to query.
* Query (go after `?` in the URL)
  * `start_date`: start date of the timeframe you wish to query - formatted as YYYY-MM-DD
  * `end_date`: inclusive end date of the timeframe you wish to query - formatted as YYYY-MM-DD
  * `cost_type`: OPTIONAL – specifies the cost type (Unblended, Public, etc.)
  * `amortization`: OPTIONAL – specifies if to include amortization
  * `exclude`: OPTIONAL – specifies if to exclude taxes, refunds, etc.
  * `granularity`: OPTIONAL – specifies the data granularity (hour, day, week, quarter, year)

{% hint style="info" %}
If the data pass **validation** a `200` status code.
{% endhint %}

{% hint style="success" %}
See the response data **schema** at the method description above.
{% endhint %}
