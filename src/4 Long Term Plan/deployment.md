**One Month Attack Plan**

Having solved the most immediate problems and having more time to work, we can actually fine tune this architecture and utilize more of the cloud resources. We will use Azure as an example but all cloud providers have the same services , only under different names.  

For client authentication we can move all IDs to Azure Entra ID and manage all authentication and authorization directly at the cloud.  

In order to maximize the elasticity of the resources, scaling up at peak hours and scaling down at night, we will convert all API layer into Azure Service Fabric services and no longer directly manage VMs. Due to this migration, we will be able to get rid of the overhead of managing the virtual machines and use our service directly on the cloud, while reducing costs even more. This layer will continue to be served behind a load balancer. 

We will move the code towards a [CQRS](https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs) pattern, in which we laid a foundation on the previous step of this migration by introducing a NoSQL database for the run operations. We will continue to move all write operations related to run to the COMMAND part of the application and have all the QUERY part from the MySQL database to serve all the dashboard operations.  
