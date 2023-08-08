# Metric Fetch

## Cost View Fetch

Cloudthread provides the ability to query your [Cost Views](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/key-concepts/cost-view).

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/cost/metric/{metric_id}" method="get" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

* `metric_id`: the ID of the Cost View you wish to query.

To query Cost Views, use the endpoint above and the following query parameters

* `start_date`: start date of the timeframe you wish to query - formatted as YYYY-MM-DD
* `end_date`: inclusive end date of the timeframe you wish to query - formatted as YYYY-MM-DD

If the data pass validation a `200` status code.

## Unit Metric Fetch

Cloudthread provides the ability to query your [Unit Metrics](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/key-concepts/unit-metric).

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/unit/metric/{metric_id}" method="get" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

* `metric_id`: the ID of the Unit Metric you wish to query.

To query Unit Metrics, use the endpoint above and the following query parameters

* `start_date`: start date of the timeframe you wish to query - formatted as YYYY-MM-DD
* `end_date`: inclusive end date of the timeframe you wish to query - formatted as YYYY-MM-DD

If the data pass validation a `200` status code.

{% hint style="info" %}
**Good to know:** All the methods shown below are synced to an example Swagger file URL and are kept up to date automatically with changes to the API.
{% endhint %}
