# Acme Fitness with Latency
---
This repository contains the manifests and code for the acme-fitness app with the ability to inject latency into the catalog service.

Please use the following manifests in order to leverage this functionality:

* For acme-frontend use manifests in either [acme-fe-azure-east](manifests/azure/acme-fe-azure-east) or [acme-fe-azure-west](manifests/azure/acme-fe-azure-west)
* for acme-backend use manifests in either [acme-be-aws-east](manifests/aws/acme-be-aws-east) or [acme-be-aws-west](manifests/aws/acme-be-aws-west)

### Adding latency to catalog service
---
Once the application is running you can add latency by opening a browser tab or using curl and navigating to the following endpoint:
```shell
http://<fqdn of acme-fitness>/catalog/addlatency/<latency in ms>
```
Here is an example:
```shell
$ curl http://latencytest.tek8s.com/catalog/addlatency/5000
{"data":"{old-latency-ms: 0, new-latency-ms: 5000}","status":200
$
```
The above example will add 5 seconds of latency to the catalog service