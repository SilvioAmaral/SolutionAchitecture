# 3 One Month Plan

![diagram](deployment.svg)

**One Month Attack Plan**

To improve the user experience for our consumers, we will do the following modifications:

In order to maximize the elasticity of the providers, we will convert all API layer into Functions (lambdas). This will allow us to only use the resources that are actually necessary for each request instead of guessing the size of the VM to host our app. 

"Azure Functions is a serverless solution that allows you to write less code, maintain less infrastructure, and save on costs. Instead of worrying about deploying and maintaining servers, the cloud infrastructure provides all the up-to-date resources needed to keep your applications running."(https://learn.microsoft.com/en-us/azure/azure-functions/functions-overview?pivots=programming-language-csharp)

Also, for the single MySQL database instance, we will create a second instance that will be focused on write only coming from the mobile apps, such as tracking data that is provided on each run. The original MySQL instance will

Although it seems that we will be utilizing more of the cloud provider, in fact we will be able to better utilize resources by scaling the app up when we need it most, such as 7AM-8AM, 12PM-01PM, 07PM-08PM, and scale down when there are almost no usage, such as during the night, from 11PM-06AM. Remember that for the time being our customer base is only the USA.


<!-- Currently we have the mobile app installed on the client directly fetching data from the API server. The installation files are served to the users phone by the respective platform marketplaces.

Our web server is already on Azure cloud, and its deployed on a single VM using IIS as a web server. The code also fetches data from the API layer. 

The API layer reads and writes all data from a single instance MySQL server. We will  -->

<!-- A deployment diagram allows you to illustrate how containers in the static model are mapped to infrastructure. This deployment diagram is based upon a UML deployment diagram, although simplified slightly to show the mapping between containers and deployment nodes. A deployment node is something like physical infrastructure (e.g. a physical server or device), virtualised infrastructure (e.g. IaaS, PaaS, a virtual machine), containerised infrastructure (e.g. a Docker container), an execution environment (e.g. a database server, Java EE web/application server, Microsoft IIS), etc. Deployment nodes can be nested.

**Scope**: A single software system.

**Primary elements**: Deployment nodes and containers within the software system in scope.

**Intended audience**: Technical people inside and outside of the software development team; including software architects, developers and operations/support staff. -->