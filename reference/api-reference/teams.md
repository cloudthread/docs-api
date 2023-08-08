# Teams

Cloudthread platform allows for manipulation of [Teams](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/fundamentals/settings/teams "mention") via an API.

{% hint style="info" %}
You can **create**, **edit**, and **delete** Teams via Cloudthread's API.
{% endhint %}

{% hint style="info" %}
See [Setting up Teams](http://127.0.0.1:5000/s/XCkDKj2xeiQhlyRGF6Wr/guides/onboarding/setting-up-teams "mention") for a guide on setting up teams through the UI.
{% endhint %}

## Team POST

Creating new team.

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/teams" method="post" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

## Team PATCH

Editing the team.

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/teams/{team_id}" method="patch" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

## Team Delete

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/teams/{team_id}" method="delete" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

## Team GET

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/teams/{team_id}" method="get" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

## Teams GET

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/teams" method="get" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

## Teams Assign Members

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/teams/{team_id}/members/assign" method="post" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

## Teams Remove Members

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/teams/{team_id}/members/delete" method="post" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

## Teams GET Members

{% swagger src="https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml" path="/teams/{team_id}/members" method="get" %}
[https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml](https://raw.githubusercontent.com/cloudthread/docs-api/main/cldthrd_api.yaml)
{% endswagger %}

{% hint style="info" %}
**Good to know:** All the methods shown below are synced to an example Swagger file URL and are kept up to date automatically with changes to the API.
{% endhint %}
