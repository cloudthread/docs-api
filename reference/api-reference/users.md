# Events Overlay Ingestion

## Event Overlay Ingestion

Cloudthread can process webhook events that can be overlayed on top of your cost data and unit metrics.

To send events data to Cloudthread, use the following endpoint and the following payload

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="api/events" method="post" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

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
* `team_id`: OPITIONAL - integer ID of the team for which the event is tied. If this value is set, only users on this team (and admins) will be able to see this event on the platform. Invalid team IDs will be rejected.
* `decscription`: text describing event.
* `type`: event type to help organize and filter events on the platform - please ensure types are consistent across events to create easy filtering.
* `event_url`: OPTIONAL - link to get more information about the sent event.

If the data pass validation and successfully save you'll receive a `201` status code.

Data sent via this API will appear in **Costs Overview** and **Unit Metrics Lab** on Cloudthread's platform.

{% hint style="info" %}
**Good to know:** All the methods shown below are synced to an example Swagger file URL and are kept up to date automatically with changes to the API.
{% endhint %}
