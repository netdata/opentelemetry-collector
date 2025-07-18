### PoC `otlpexporter` with Unix Domain Sockets support
#### How-to
1. Install OTel Collector `builder` utility ([link](https://opentelemetry.io/docs/collector/custom-collector/#step-1---install-the-builder)).  


2. Build an OTel Collector with the updated `otlpexporter` that supports unix domain sockets, using the provided [builder-config.yaml](builder-config.yaml)

```shell
  builder --config builder-config.yaml
```

3. Start the _destination_ OTel Collector instance

```shell
  ./build/otelcollector --config=file:./to.yaml
```

4. Start the _origin_ OTel Collector instance. Run it as an admin if you want to avoid any issues accessing information about running processes (e.g _error reading process executable for pid_ XXX)

```shell
  sudo ./build/otelcollector --config=file:./from.yaml
```

