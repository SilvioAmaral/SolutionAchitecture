**One Month Attack Plan**

Having solved the most immediate problems and having more time to work, we can actually fine tune this architecture and utilize more of the cloud resources, moving all services to the cloud. We will use Azure as an example but all cloud providers have the same services , only under different names.  

For client authentication we can move all IDs to Azure Entra ID and manage all authentication and authorization directly at the cloud.  

In order to maximize the elasticity of the resources, scaling up at peak hours and scaling down at night, we will convert all API layer into Azure Service Fabric services. Due to this migration , we will be able to get rid of the overhead of managing the virtual machines and use our service directly on the cloud, while reducing costs even more.

Since our services are still scalable , we will still need a load balancer layer to manage the many instances running  

Also, the mobile app will be modified to send each individual point of the tracking data at a smaller interval, therefore avoiding large chunks of data coming in at once. Therefore the "STOP RUN" functionality of our app will only carry the overall run directly to the dashboard tables. 

For the Database server we will create a second Database responsible for write-intensive GPS tracking data that is provided on each run coming from the mobile apps via API. This aims to remove the load from the tables that are currently responsible for read operations of dashboard data.
