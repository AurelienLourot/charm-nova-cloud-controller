# Temporary fork of [charm-nova-cloud-controller](https://github.com/openstack/charm-nova-cloud-controller)

Containing [this fix](https://review.opendev.org/c/openstack/charm-nova-cloud-controller/+/775900).

## Publishing to the store

```
$ charm login
$ touch /tmp/dummy-policyd-override.zip
$ charm push . cs:~aurelien-lourot/nova-cloud-controller \
    -r policyd-override=/tmp/dummy-policyd-override.zip
url: cs:~aurelien-lourot/nova-cloud-controller-0
channel: unpublished
Uploaded "/tmp/dummy-policyd-override.zip" as policyd-override-0
$ charm release cs:~aurelien-lourot/nova-cloud-controller-0 --resource policyd-override-0
url: cs:~aurelien-lourot/nova-cloud-controller-0
channel: stable
warning: bugs-url and homepage are not set.  See set command.
$ charm set cs:~aurelien-lourot/nova-cloud-controller \
    homepage=https://github.com/AurelienLourot/charm-nova-cloud-controller/tree/bug/1915504
$ charm grant cs:~aurelien-lourot/nova-cloud-controller-0 --acl read everyone
```

The published charm can be found
[here](https://jaas.ai/u/aurelien-lourot/nova-cloud-controller).
