# 1 System Context Diagram

![diagram](system.svg)

**Level 1: System Context**

The system context diagram represents a high-level overview of the interactions of the main components of the current architecture.

**Primary Elements**

There are currently one main user and two main components on this application. The primary elements are as follow:

- Our main users are runners that want to track and improve their running habits. These persons range from teens to seniors of all genders. 

- The first main component is the mobile application, designed to allow users to select a running program, track their runs with GPS data , count calories of each run , and enhance the running experience with a music playlist. 

- The second main component is a web dashboard that is designed to give users an overview of their runs and track their progress over time. They can also manage their accounts and purchase advanced plans with live trainer support.

**Secondary Elements**

- Trainers are professional runners that provide services guiding our beginner runners into their journey. They are considered External persons to our application, as they connect directly to the customer via external providers (zoom, webex). We will no longer be listing the trainers on our diagrams, as it is not a source of problems and therefore not the main focus of this optimization project.

**Analysis of problems**

As listed on our overview page, some of the main problems we have are:

- the app is not responsive during a run, especially trying to start and stop it

Let's consider that the responsiveness issue  is due to the mobile app storing all data points during the run and performing one single POST with all data to the API once. This can cause the server to have spikes in utilization, both on service and database.

- some customers mentioned that their runs are disappearing from the web dashboard

Due to the amount of data that the mobile app accumulates, sometimes the app crashes or sometimes the upload of data fails silently, therefore never showing on dashboard. 

- when customers finish a run, it takes more than one day to view on the dashboard

Let's consider for this scenario that the data written on the DB after each run gets processed overnight on a batch process so it can be displayed to the user at the dashboard part of the application. 
