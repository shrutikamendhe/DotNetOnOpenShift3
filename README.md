# Enable .NET Support on OpenShift 3 Enterprise
This repository contains guide line to enable .Net support on OpenShift 3 Enterprise. Follow below instruction to deploy Click2Cloud's .NET Builder Images and Templates to run .NET applications in container on OpenShift 3 Cloud.

### Deploy Builder Image on OpenShift 3
Run below command in all Nodes of OpenShift
```
$ docker pull click2cloud/aspnet-s2i-4.5
$ docker pull click2cloud/aspnet-s2i-core-1.0
```
This will pull Click2Cloud's .NET Builder Images from Docker Hub.

### Install .NET Image Stream
Once you have pulled .NET Builder Images, it is required to define it in Image Stream list. Download and save `aspnet-4.5-imagestream.json` file and `aspnet-5.0-imagestream.json` onto OpenShift 3 Master Node. Navigate to location on OpenShift Master Node where you have saved json files and run below command as a `root` user.
```
$ oc create -f aspnet-4.5-imagestream.json -n openshift
$ oc create -f aspnet-5.0-imagestream.json -n openshift
```
### Install .NET Templates
To install .NET Templates provided by Click2Cloud, download and save all template files from this repository onto OpenShift 3 Master Node. Navigate to location on OpenShift Master Node where you have saved template files and run below command as a `root` user.
```
$ oc create -f aspnet-4.5-template.json -n openshift
$ oc create -f aspnet-4.5-externaldb-template.json -n openshift
$ oc create -f aspnet-4.5-mongodb-template.json -n openshift
$ oc create -f aspnet-4.5-mysql-template.json -n openshift
$ oc create -f aspnet-4.5-postgresql-template.json -n openshift
$ oc create -f aspnet-5.0-template.json -n openshift
$ oc create -f aspnet-5.0-externaldb-template.json -n openshift
$ oc create -f aspnet-5.0-mongodb-template.json -n openshift
$ oc create -f aspnet-5.0-mysql-template.json -n openshift
$ oc create -f aspnet-5.0-postgresql-template.json -n openshift
```
After installing .NET Templates, verify it from OpenShift Web Console.
