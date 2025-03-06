# Using the prometheus database for data collection

The prometheus database is used for many projects for data collection. It is relatively easy to set up and use.

For installation, you can follow a [guide provided by the prometheus devs](https://prometheus.io/docs/introduction/first_steps/).

Here are some distro-specific guides for linux:

- Debian/Ubuntu/Raspbian: [See this guide here](https://gist.github.com/eiri/1102e1f3c168684b5a8b0e7a0f5a5a14) (Although there should also be something in the APT repos)
- Archlinux: [Archlinux Wiki / Prometheus](https://wiki.archlinux.org/title/Prometheus)

### Configuring Prometheus to scrape data from the OpenDTU
```yaml
# /etc/prometheus/prometheus.yml
scrape_configs:
  - job_name: 'opendtu'
    scrape_interval: 5s # >= Inverter scrape interval
    static_configs:
    - targets: ['<ip of first opendtu>', '<ip of second opendtu>']
    metrics_path: /api/prometheus/metrics
```

### Example Grafana Dashboards
- [https://grafana.com/grafana/dashboards/19666-opendtu/](https://grafana.com/grafana/dashboards/19666-opendtu/)
- [https://github.com/tbnobody/OpenDTU/discussions/1230#discussioncomment-6969028](https://github.com/tbnobody/OpenDTU/discussions/1230#discussioncomment-6969028)
