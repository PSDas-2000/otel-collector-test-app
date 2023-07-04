# otel-collector-test-app
Test application for using otel-collector as Prometheus and then send it to Prometheus.
Purpose is to test viability of the otel-collector as a prometheus scraper, which can later be used with a third-party backend or another prometheus.

Uses a test nodejs app which exposes default prometheus metrics as a docker image. Other images are official images from the official prometheus and otel websites.  

# Instructions
  1) Clone this repository
  2) Navigate to root of local repository
  3) Run: </br> ```docker compose up```

# Follow up
After running the compose project, you can check the progress by running the following on your web browser:
  1) localhost:80/metrics -> Shows metrics exposed locally by application
  2) localhost:8888/metrics -> Shows metrics for the otel-collector app
  3) localhost:1234/metrics -> All metrics collected by the collector (can take up to 10s because of prometheus rules in the otel-collector-config.yaml)
  4) localhost:9090/ -> Access prometheus for queries 
     Prometheus can show you metrics from both the nodejs app (search for nodejs) and the otel-collector app (search for otel). This can take up to 10-12s because of the prometheus rule in the prometheus.yaml.

# Warnings
 * otel-collector's prometheus receiver is still in development and does not support all prometheus features yet. ([Read more](https://github.com/open-telemetry/opentelemetry-collector-contrib/blob/main/receiver/prometheusreceiver/README.md#%EF%B8%8F-warning))
 * the location of the otel-collector config is a manual location set inside docker compose using 'command' in the otel-collector service. The default location is '/etc/otelcol-contrib/config.yaml'
