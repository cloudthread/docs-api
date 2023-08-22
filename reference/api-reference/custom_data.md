# Data Ingestion

Cloudthread can process custom data for generating [Cost Views](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/key-concepts/cost-view "mention") and [Unit Metrics](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/key-concepts/unit-metric "mention").

In order to send custom data, you must provision a **Custom Data - Data Stream Token** on the Cloudthread platform within the [Settings](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/settings "mention") tab.

{% hint style="info" %}
See more in [Ingesting Custom Data](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/guides/monitoring-cloud-costs/ingesting-custom-data "mention") guide.
{% endhint %}

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/streams/ingest" method="post" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

To send custom data to Cloudthread, use the endpoint above with the provisioned **Data Stream Token** and the following payload:

```json
{
  data_stream_token: {DATA_STREAM_TOKEN},
  metric_agg_func: 'Sum' | 'Average' | 'Maximum' | 'Minimum',
  data: [
    {
      timestamp: datetime,
      metric_name: string,
      metric_value: float,
      custom_dimensions: {
        string: string,
        ...
      }
    },
    ...
  ]
}
```

* `metric_agg_func`: aggregation function across the dataset. _Do not_ include data with different aggregation methods into the same request.
* `timestamp`: datetime with **hourly** granularity. Any timestamp with minutes, seconds, etc. will be rejected. E.g. `'2022-10-01 00:00:00'`. To send daily data, send data with the timepart = `00:00:00`.
* `metric_name`: name of the metric -- all metrics that share a name and aggregation function will be grouped together by date given the prescribed aggregation function. This means you can up have up to four versions of the same metric name based on different aggregation functions.
* `mertic_value`: float convertiable value of the metric.
* `custom_dimensions`: map of **up to 10** key value pairs that you will be able to segment the data by on the Cloudthread platform.

{% hint style="success" %}
If the data pass **validation** and successfully save you'll receive a `201` status code.
{% endhint %}

* Cloudthread creates a record ID for each data point by hashing the metric name, metric aggregation function, and the custom dimensions into a single key.
* To update a data point that's already been sent, the incoming data point must match along these fields -- otherwise a new data point will be generated.
* You can then update a given timestamp and metric value pair by sending in the matching timestamp with a new metric value.
