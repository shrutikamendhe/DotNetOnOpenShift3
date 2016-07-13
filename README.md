# Run .NET Application on OpenShift 3
This repository contains guide line to host and run .NET based applications on OpenShift 3 Cloud. Below instructions guide you to deploy Click2Cloud's .NET Templates for all users, if you have access to OpenShift Master node. Also, at project level, if you have limited access.

### Deploy Templates for all users
If you have access to OpenShift 3 Master node and can deploy templates at `openshift` project level, follow below steps.

##### Clone DotNetOnOpenShift3 repository
```
git clone https://github.com/Click2Cloud/DotNetOnOpenShift3.git
cd DotNetOnOpenShift3
```
#### Install .NET Templates
Login to OpenShift 3 Master node as a `root` user and run below commands. 

##### To Install ASP.NET 4.5 Templates
```
oc create -f aspnet-4.5-template.json -n openshift
oc create -f aspnet-4.5-externaldb-template.json -n openshift
oc create -f aspnet-4.5-mongodb-template.json -n openshift
oc create -f aspnet-4.5-mysql-template.json -n openshift
oc create -f aspnet-4.5-postgresql-template.json -n openshift
```
##### To Install ASP.NET 5.0 Templates
```
oc create -f aspnet-5.0-template.json -n openshift
oc create -f aspnet-5.0-externaldb-template.json -n openshift
oc create -f aspnet-5.0-mongodb-template.json -n openshift
oc create -f aspnet-5.0-mysql-template.json -n openshift
oc create -f aspnet-5.0-postgresql-template.json -n openshift
```
After installing .NET Templates, verify it from OpenShift Web Console. You should get following result after searching `ASPNET` in `Select Image or Template` page.

![Search Result](/result.png?raw=true "Result")
