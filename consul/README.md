## Build

```
docker build -t kelseyhightower/consul .
```

## Usage

### Run consul as the first node in the cluster

```
docker run -d -P kelseyhightower/consul -bootstrap -client 0.0.0.0 -server
```

### Run consul with the web UI

The `/opt/consul/web_ui` directory is bundled in the container.

```
docker run -d -P kelseyhightower/consul -bootstrap -client 0.0.0.0 -server -ui-dir /opt/consul/web_ui
```
