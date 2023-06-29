# otel-collector-test-app
Test application for using otel-collector as Prometheus and then send it to Prometheus.
Purpose is to test viability of the otel-collector as a prometheus scraper, which can later be used with a third-party backend or another prometheus.

Uses a test nodejs app which exposes default prometheus metrics as a docker image. Other images are official images from the official prometheus and otel websites.  

# Warnings
 * otel-collector's prometheus receiver is still in development and does not support all prometheus features yet. ([Read more](https://github.com/open-telemetry/opentelemetry-collector-contrib/blob/main/receiver/prometheusreceiver/README.md#%EF%B8%8F-warning))
