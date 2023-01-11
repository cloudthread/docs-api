# Data Ingestion

Cloudthread can process custom data for generating views and unit metrics.

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/api/streams/ingest" method="post" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

To send custom data to Cloudthread, use the **Data Ingestion** endpoint above with the provisioned Data Stream Token and the following payload

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

If the data pass validation and successfully save you'll receive a `201` status code.

Cloudthread creates a record ID for each data point by hashing the metric name, metric aggreation function, and the custom dimensions into a single key. To update a data point that's already been sent, the incoming data point must match along these fields -- otherwise a new data point will be generated. You can then update a given timestamp and metric value pair by sending in the matching timestamp with a new metric value.

**Good to know:** This API method was auto-generated from an example Swagger file. You'll see that it's not editable – that's because the contents are synced to a URL! Any time the linked file changes, the documentation will change too.
