# Common.BlackBoxExporter

Install BlackBoxExporter

# Changelog

## 2.0.2

- Radmir fixes

## 1.0.0

- Pass datname var to postgres dashboard

# Documentation for 2.0.2

## Variables

### Non-secret

All variables are set by default

```yaml
blackbox_exporter:
  docker_image: docker-proxy-pub.avant-it.ru/prometheus/blackbox-exporter:v0.24.0
  config_template_path: templates/blackbox-exporter/config.yaml.j2
  container_port: 9115
  port: 9115
```

### Secret

```yaml
```

## Example of config.yaml 1

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

## Example of config.yaml 2

```yaml
modules:

  up:
    prober: http
    timeout: 10s
    http:
      method: GET
      no_follow_redirects: false
      valid_status_codes: [200]
      fail_if_ssl: false
      fail_if_not_ssl: true
      fail_if_body_not_matches_regexp: 
      - "end_booking_widget-mobile|lalala|dasdasdedfsfsdf"
      preferred_ip_protocol: "ip4"
```