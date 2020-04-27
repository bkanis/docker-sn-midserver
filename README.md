[![License MIT](https://img.shields.io/badge/license-ISC-blue.svg)](https://opensource.org/licenses/ISC) [![](https://img.shields.io/docker/pulls/andrekosak/sn-midserver.svg)](https://hub.docker.com/r/andrekosak/sn-midserver 'DockerHub') [![](https://ga-beacon.appspot.com/UA-82522402-3/readme?pixel)](https://github.com/igrigorik/ga-beacon)


## Get started right away

```bash
$ docker run -d --name sn-mid-server \
  -e 'SN_URL=https://dev00000.service-now.com' \
  -e 'SN_USER=username' \
  -e 'SN_PASSWD=userpassword' \
  -e 'SN_MID_NAME=sn-mid-server' \
  andrekosak/sn-midserver:kingston
```

or using Docker Compose:

```yaml
version: '3'
services:
  midserver:
    container_name: sn-midserver
    image: andrekosak/sn-midserver:kingston
    network_mode: host
    environment:
      - SN_URL=https://dev00000.service-now.com
      - SN_USER=username
      - SN_PASSWD=password
      - SN_MID_NAME=my-mid-server
```

# Persisting logs

```bash
$ docker run -d --name sn-mid-server \
  -e 'SN_URL=https://dev00000.service-now.com' \
  -e 'SN_USER=username' \
  -e 'SN_PASSWD=password' \
  -e 'SN_MID_NAME=my-mid-server' \
  -v './sn-midserver/logs:/opt/agent/logs' \
  andrekosak/sn-midserver:kingston
```

or using Docker Compose:

```yaml
version: '3'
services:
  midserver:
    container_name: sn-midserver
    image: andrekosak/sn-midserver:kingston
    volumes:
      - ./sn-midserver/logs:/opt/agent/logs
    network_mode: host
    environment:
      - SN_URL=https://dev00000.service-now.com
      - SN_USER=username
      - SN_PASSWD=password
      - SN_MID_NAME=my-mid-server
```