# Common.BlackBoxExporter

Install BlackBoxExporter

# Changelog

## 2.0.1

- Radmir fixes

## 2.0.0

- fix

## 1.0.0

- Pass datname var to postgres dashboard

# Documentation

All variables are set by default

```yaml
blackbox_exporter:
  docker_image: docker-proxy-pub.avant-it.ru/prometheus/blackbox-exporter:v0.24.0
  container_port: 9115
  port: 9115
```

All variables

Example
https://gitlab.avant-it.ru/main/k2t/infrastructure/development/k2t.yc.prometheus/-/blob/master/group_vars/main.yml#L131


```yaml
blackbox_exporter:
  docker_image: docker-proxy-pub.avant-it.ru/prometheus/blackbox-exporter:v0.24.0
  container_port: 9115
  port: 9115
  config_path: config/blackbox-exporter.yml # path for config

```


Example of config.yaml

```yaml
modules:
  http_2xx:
    prober: http
    timeout: 30s
    http:
      valid_http_versions: ["HTTP/1.1", "HTTP/2.0"]
      preferred_ip_protocol: "ip4"
      valid_status_codes: [200, 404, 400, 403, 405, 302, 307]  # Defaults to 2xx

```
