# Example - Connect Go App to dash0

This is an example of how the Go application can be connected to dash0 based on the official article [Getting Started](https://opentelemetry.io/docs/languages/go/getting-started/).
The application and the OpenTelemetry Collector can be started as follows.

```sh
> export BEARER_TOKEN=[YOUR_DASH0_ORG_AUTH_TOKEN]
> export DASH0_ENDPOINT=[DASH0_URL_WITH_PORT]
> docker compose up --build
```

Once both Docker containers have been successfully started
the application can be opened at <http://localhost:8080/rolldice>.

If everything works correctly, you should now see the logs, traces and metrics at dash0.
