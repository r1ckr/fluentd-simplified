# Fluentd Simplified

This repo is used as the source code of [this](https://scaleout.ninja/post/fluentd-simplified/) post.

## Run Fluentd
```bash
docker run -ti --rm \
-v $(pwd)/etc:/fluentd/etc \
-v $(pwd)/log:/var/log/ \
-v $(pwd)/output:/output \
fluent/fluentd:v1.10-debian-1 -c /fluentd/etc/fluentd.conf -v
```

## Run Fluentd with plugin
```bash
docker run -u root -ti --rm \
-v $(pwd)/etc:/fluentd/etc \
-v $(pwd)/log:/var/log/ \
-v $(pwd)/output:/output \
fluent/fluentd:v1.10-debian-1 bash -c "gem install fluent-plugin-rewrite-tag-filter && fluentd -c /fluentd/etc/fluentd.conf -v"
```