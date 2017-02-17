Customizations for OpenShift Logging Elasticsearch
==================================================

During the upgrade to Elasticsearch 2.3.5 OpenShift's aggregated logging
[tightened the access controls around
resources](https://github.com/openshift/origin-aggregated-logging/commit/b7f526dc6dfabf1a98db)
used by monitoring. In order to continue to monitor the cluster it's necessary
to grant the monitoring service user the necessary permissions.

Installation
------------

Either on a master node in the cluster or from a machine with `oc` logged into
the cluster with `cluster-admin` permissions:

```
./deploy

# Specific version
image_tag=v1.4.1 ./deploy
```


Uninstallation
--------------

```
oc delete all -l group=logging-elasticsearch-appu
```

<!-- vim: set sw=2 sts=2 et : -->
