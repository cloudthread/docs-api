# Events Overlay Ingestion

## Event Overlay Ingestion

Cloudthread can process **webhook events** that can be overlayed on top of your [Cost Views](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/key-concepts/cost-view "mention") and [Unit Metrics](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/key-concepts/unit-metric "mention").

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/events" method="post" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

To send events data to Cloudthread, use the endpoint above and the following payload:

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
* `team_id`: OPITIONAL – integer ID of the team for which the event is tied. If this value is set, only users on this team (and admins) will be able to see this event on the platform. Invalid team IDs will be rejected.
* `decscription`: text describing event.
* `type`: event type to help organize and filter events on the platform – please ensure types are consistent across events to create easy filtering.
* `event_url`: OPTIONAL – link to get more information about the sent event.

{% hint style="success" %}
If the data pass **validation** and successfully save you'll receive a `201` status code.
{% endhint %}

Data sent via this API will appear in [Costs Overview](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/cost-transparency/costs-overview "mention") and [Unit Metrics Lab](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/unit-metrics/unit-metrics-lab "mention") on Cloudthread's platform.
