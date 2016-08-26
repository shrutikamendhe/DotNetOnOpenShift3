# Run .NET Application on OpenShift 3
This repository contains guide line to host and run .NET based applications on OpenShift 3 Cloud. Below instructions guide you to deploy Click2Cloud's .NET Templates for all users, if you have access to OpenShift Master node. Also, at project level, if you have limited access.

##### Clone DotNetOnOpenShift3 repository
```
git clone https://github.com/Click2Cloud/DotNetOnOpenShift3.git
cd DotNetOnOpenShift3
```

### Deploy Templates for all users
If you have access to OpenShift 3 Master node and can deploy templates at `openshift` project level, follow below steps.

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
oc create -f aspnet-core-1.0-template.json -n openshift
oc create -f aspnet-core-1.0-externaldb-template.json -n openshift
oc create -f aspnet-core-1.0-mongodb-template.json -n openshift
oc create -f aspnet-core-1.0-mysql-template.json -n openshift
oc create -f aspnet-core-1.0-postgresql-template.json -n openshift
```
After installing .NET Templates, verify it from OpenShift Web Console. You should get following result after searching `asp` in `Select Image or Template` page.

![Search Result](/result.png?raw=true "Result")

### Deploy Templates at project level
If you do not have access to OpenShift 3 Master node, follow instruction below to deploy Templates at project level.

#### Install .NET Templates
Login to OpenShift 3 using CLI and select the project where you want to install .NET Templates. 

##### Select project
```
oc project <projectname>
```

##### To Install ASP.NET 4.5 Templates
```
oc create -f aspnet-4.5-template.json
oc create -f aspnet-4.5-externaldb-template.json
oc create -f aspnet-4.5-mongodb-template.json
oc create -f aspnet-4.5-mysql-template.json
oc create -f aspnet-4.5-postgresql-template.json
```
##### To Install ASP.NET 5.0 Templates
```
oc create -f aspnet-core-1.0-template.json
oc create -f aspnet-core-1.0-externaldb-template.json
oc create -f aspnet-core-1.0-mongodb-template.json
oc create -f aspnet-core-1.0-mysql-template.json
oc create -f aspnet-core-1.0-postgresql-template.json
```

## Compatible Test run on below environment for templates

| Template        | OpenShift Enterprise | OpenShift Origin  |
| --------------- |:-----------------:| :-----:|
| aspnet-4.5-template      | Yes| Yes |
| aspnet-4.5-externaldb-template      | Yes      |   Yes |
| aspnet-4.5-mongodb-template | Yes      |    Yes |
| aspnet-4.5-mysql-template | Yes      |    Yes |
| aspnet-4.5-postgresql-template | Yes      |    Yes |
| aspnet-core-1.0-template | Yes      |    Yes |
| aspnet-core-1.0-externaldb-template | Yes      |    Yes |
| aspnet-core-1.0-mongodb-template | Yes      |    Yes |
| aspnet-core-1.0-mysql-template | Yes      |    Yes |
| aspnet-core-1.0-postgresql-template | Yes      |    Yes |

NOTE: This version is not tested on OpenShift Online Environment.