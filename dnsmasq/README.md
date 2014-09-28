# dnsmasq Dockerfile

## Usage

```
docker pull quay.io/kelseyhightower/dnsmasq
```

### Configuration and data

```
/etc/dnsmasq.conf
```

```
sudo mkdir -p /var/lib/tftpboot
```

```
docker run -d --net=host -v /etc/dnsmasq.conf:/etc/dnsmasq.conf \
-v /var/lib/tftpboot:/var/lib/tftpboot \
quay.io/kelseyhightower/dnsmasq
```

## Build

```
docker build -t quay.io/kelseyhightower/dnsmasq . 
```
