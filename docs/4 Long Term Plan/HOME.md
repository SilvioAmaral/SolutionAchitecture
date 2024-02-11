# 4 Long Term Plan

![diagram](deployment.svg)

**One Month Attack Plan**

Having solved the most immediate problems and having more time to work, we can actually fine tune this architecture and utilize more of the cloud resources. 

In order to maximize the elasticity of the resources, scaling up at peak hours and scaling down at night, we will convert all API layer into lambda functions. Due to this migration , we will be able to reduce the size of the actual VM Instance 1, since it will only be used to serve static content and the SPA app.

Also, the mobile app will be modified to send each individual point of the tracking data at a smaller interval, therefore avoiding large chunks of data coming in at once. Therefore the "STOP RUN" functionality of our app will only carry the overall run directly to the dashboard tables. 

For the Database server we will create a second Database responsible for write-intensive GPS tracking data that is provided on each run coming from the mobile apps via API. This aims to remove the load from the tables that are currently responsible for read operations of dashboard data.
