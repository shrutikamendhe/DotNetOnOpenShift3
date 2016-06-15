# Enable .NET Support on OpenShift 3
This repository contains guide line to enable .NET support on OpenShift 3 Cloud. Follow below instruction to deploy Click2Cloud's .NET Builder Images and Templates to run .NET applications in container on OpenShift 3.

### 1) Pull Builder Image on OpenShift 3
Run below command in all Nodes of OpenShift
```
$ docker pull click2cloud/aspnet-s2i-core-1.0
$ docker pull click2cloud/aspnet-4.5-centos7 
OR
$ docker pull click2cloud/aspnet-4.5-rhel7
```

This will pull Click2Cloud's .NET Builder Images from Docker Hub onto OpenShift 3 Nodes.

### 2) Install .NET Image Stream
Once you have pulled .NET Builder Images, it is required to define it in Imagestream list. Login to OpenShift 3 Master node and run below commands as a `root` user.

##### Clone DotNetOnOpenShift3 repository
```
$ git clone https://github.com/Click2Cloud/DotNetOnOpenShift3.git
$ cd DotNetOnOpenShift3
```
#### For ASP.NET 4.5 image
```
$ oc create -f aspnet-4.5-centos-imagestream.json -n openshift
OR
$ oc create -f aspnet-4.5-rhel-imagestream.json -n openshift
```
#### For ASP.NET 5.0 image On OpenShift 3 Enterprise
```
$ oc create -f aspnet-5.0-imagestream.json -n openshift
```
#### For ASP.NET 5.0 image On OpenShift 3 Origin
```
$ oc create -f aspnet-5.0-imagestream-origin.json -n openshift
```
### Install .NET Templates
After installing imagestream, install .NET templates provided by Click2Cloud run below commands as a `root` user. 

#### To Install ASP.NET 4.5 Templates
```
$ oc create -f aspnet-4.5-template.json -n openshift
$ oc create -f aspnet-4.5-externaldb-template.json -n openshift
$ oc create -f aspnet-4.5-mongodb-template.json -n openshift
$ oc create -f aspnet-4.5-mysql-template.json -n openshift
$ oc create -f aspnet-4.5-postgresql-template.json -n openshift
```
#### To Install ASP.NET 5.0 Templates
```
$ oc create -f aspnet-5.0-template.json -n openshift
$ oc create -f aspnet-5.0-externaldb-template.json -n openshift
$ oc create -f aspnet-5.0-mongodb-template.json -n openshift
$ oc create -f aspnet-5.0-mysql-template.json -n openshift
$ oc create -f aspnet-5.0-postgresql-template.json -n openshift
```
After installing .NET Templates, verify it from OpenShift Web Console. You should get following result after searching `ASPNET` in `Select Image or Template` page.

![Search Result](/result.png?raw=true "Result")
