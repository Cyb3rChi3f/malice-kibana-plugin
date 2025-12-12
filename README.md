# malice-kibana-plugin

[![Circle CI](https://circleci.com/gh/maliceio/malice-kibana-plugin.png?style=shield)](https://circleci.com/gh/maliceio/malice-kibana-plugin) [![License](https://img.shields.io/badge/licence-Apache%202.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)

> Malice Kibana Plugin

![screen-shot](https://raw.githubusercontent.com/Cyb3rChi3f/malice-kibana-plugin/master/docs/new-screen.png)

---

#### Requirements

- Kibana 7.0.0+

## installation

```sh
kibana-plugin install \
         https://github.com/Cyb3rChi3f/malice-kibana-plugin/releases/download/v7.0.0/malice-7.0.0.zip
```

## development

```sh
git clone https://github.com/Cyb3rChi3f/malice-kibana-plugin.git
cd malice-kibana-plugin
# start plugin
make run
```

=OR=

Start Kibana's Elasticsearch

```bash
$ docker run --init -d \
             --name kplug \
             -p 9200:9200 \
             -p 5601:5601 \
             -v `pwd`:/plugin/kibana-extra/malice \
             blacktop/kibana-plugin-builder elasticsearch
```

> **NOTE:** elasticsearch takes a while to start

Install plugin `node_modules`

```sh
docker exec -it kplug bash -c "cd ../kibana-extra/malice && yarn kbn bootstrap"
```

Add some scan data

```sh
docker exec -it kplug bash -c "cd ../kibana-extra/malice/data && ./load-data.sh"
```

Start Kibana Plugin

```sh
docker exec -it kplug bash -c "cd ../kibana-extra/malice && ./start.sh"
```

Open [https://localhost:5601/](https://localhost:5601/)

---

## issues

Find a bug? Want more features? Find something missing in the documentation? Let me know! Please don't hesitate to [file an issue](https://github.com/Cyb3rChi3f/malice-kibana-plugin/issues/new)

## changelog

See [`CHANGELOG.md`](https://github.com/Cyb3rChi3f/malice-kibana-plugin/blob/master/CHANGELOG.md)

## contributing

[See all contributors on GitHub](https://github.com/Cyb3rChi3f/malice-kibana-plugin/graphs/contributors).

Please update the [CHANGELOG.md](https://github.com/Cyb3rChi3f/malice-kibana-plugin/blob/master/CHANGELOG.md) and submit a [Pull Request on GitHub](https://help.github.com/articles/using-pull-requests/).

## license

Apache License (Version 2.0)
Copyright (c) 2013 **blacktop** Joshua Maine
