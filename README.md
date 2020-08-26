# nvidia_smi_exporter

nvidia-smi metrics exporter for Prometheus

## Build
```
> go build -v smi_exporter.go
```

## Run
```
> ./smi_exporter [<port>]
```
Default port is 9101


### localhost:9101/metrics

### Exact command
```
nvidia-smi --query-gpu=name,index,temperature.gpu,utilization.gpu,utilization.memory,memory.total,memory.free,memory.used --format=csv,noheader,nounits
```

### Prometheus example config

```
- job_name: "gpu_exporter"
  static_configs:
  - targets: ['localhost:9101']
```

