# Developer API

Cloudthread provides a powerful and flexible REST Developer API to help you get the most out of your data.

This page shows how to use the API, and what features are currently available.

## Basic setup

Cloudthread's Developer API lives at

`https://api.cloudthread.io`

Cloudthread requires an API Token to process incoming developer API requests. Admin's have the ability to generate API Tokens on the Cloudthread platform within the **Settings** tab.

This API Token should be included in the headers for all Developer API requests as follows:

`x-api-key: {API_TOKEN}`

Any request without a valid token will be rejected.

## Data Ingestion

Cloudthread provides the abiilty to send data to our systems that can then be used on the platform.

Cloudthread requires a **Data Stream Token** to process incoming Data Ingestion API requests. This token helps organize and control the flow of data. Data Stream Tokens are generated with a **Data Stream Type** that determines how the incoming data is validated. Admin's have the ability to generate a Data Stream Token on the Cloudthread platform within the **Settings** tab.

This Data Stream Token should be included in the body of incoming ingestion requests as demonstrated in the payload examples below.

All ingestion requests use the following endpoint

`https://api.cloudthread.io/streams/ingest`

## Custom Data Ingestion

Cloudthread can process custom data to help customers understand their non-cost data as it relates to their cost data.

In order to send custom data, you must provision a **Custom Data - Data Stream Token** on the Cloudthread platform within the **Settings** tab.

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

* `metric_agg_func`: aggregation function across the dataset. *Do not* include data with different aggregation methods into the same request.
* `timestamp`: datetime with **hourly** granularity. Any timestamp with minutes, seconds, etc. will be rejected. E.g. `'2022-10-01 00:00:00'`. To send daily data, send data with the timepart = `00:00:00`.
* `metric_name`: name of the metric -- all metrics that share a name and aggregation function will be grouped together by date given the prescribed aggregation function. This means you can up have up to four versions of the same metric name based on different aggregation functions.
* `mertic_value`: float convertiable value of the metric.
* `custom_dimensions`: map of **up to 10** key value pairs that you will be able to segment the data by on the Cloudthread platform.

If the data pass validation and successfully save you'll receive a `201` status code.

Cloudthread creates a record ID for each data point by hashing the metric name, metric aggreation function, and the custom dimensions into a single key. To update a data point that's already been sent, the incoming data point must match along these fields -- otherwise a new data point will be generated. You can then update a given timestamp and metric value pair by sending in the matching timestamp with a new metric value.

Data sent via this API will appear in the **Unit Metrics Lab** on Cloudthread's platform.

## Event Overlay Ingestion

Cloudthread can process webhook events that can be overlayed on top of your cost data and unit metrics.

To send events data to Cloudthread, use the following endpoint and the following payload

`https://api.cloudthread.io/events`

```json
{
  data: [
    {
      timestamp: datetime,
      team_id?: int,
      payload: {
        decscription: string (max length 1000),
        type: string,
        event_url?: string,
      }
    },
    ...
  ]
}
```

* `timestamp`: datetime with **hourly** granularity. Any timestamp with minutes, seconds, etc. will be rejected. E.g. `'2022-10-01 00:00:00'`. To send daily data, send data with the timepart = `00:00:00`.
* `team_id`: OPITIONAL - integer ID of the team for which the event is tied.  If this value is set, only users on this team (and admins) will be able to see this event on the platform. Invalid team IDs will be rejected.
* `decscription`: text describing event.
* `type`: event type to help organize and filter events on the platform - please ensure types are consistent across events to create easy filtering.
* `event_url`: OPTIONAL - link to get more information about the sent event.

If the data pass validation and successfully save you'll receive a `201` status code.

Data sent via this API will appear in **Costs Overview** and **Unit Metrics Lab** on Cloudthread's platform.


##COMING SOON - Data querying API

Please contact support@cloudthread.io for more information about this feature
