# Architecture Project #1

* [Overview: Running App](#Overview:-Running-App)
  * [1 System Context Diagram](#1-System-Context-Diagram)
    * [Container Diagram](#Container-Diagram)
      * [API App Component](#API-App-Component)
      * [Mobile App Component](#Mobile-App-Component)
      * [Web App Component](#Web-App-Component)
  * [2 Current Deployment Diagram](#2-Current-Deployment-Diagram)
  * [3 One Month Plan](#3-One-Month-Plan)
  * [4 Long Term Plan](#4-Long-Term-Plan)

---

## Overview: Running App

# Software Architecture Course

**Project Part 1**

The goal of the running application is to allow users to track their running habits and get motivated by visualizing their progress.

Unfortunately, customers have been complaining about some problems, and our business is losing customers to the competition. 

In this document we have devised a one month plan to tackle the three immediate pain points with an improve in our software architecture.

**Primary Goals**

- the app is not responsive during a run, especially trying to start and stop it
- some customers mentioned that their runs are disappearing from the web dashboard
- when customers finish a run, it takes more than one day to view on the dashboard

**Secondary Goals**

- Reduce cost of total cloud account

**Scope**: Our Running application System and their interactions

**Intended audience**: CEO, CTO, and CFO are the primary audience for this presentation. Eventually it will be extended to the development team in order to provide clarity on the goals to follow ahead.

**Assumptions**: 

- The dev team is capable to work on the code and provide required refactoring. 
- The devops team is capable to work and manage our cloud provider   
- The QA team can actually reproduce the issues and test the app is running.
- No staff change is likely to happen on the suggested time frame.
- We will utilize a bit over half the IT team separated at 3 teams of 6 devs/devops/qa, for 2 consecutive sprints. 
- The allocation of staff is agreed upon and no changes to the plan will be done on the next month

**Limitations**: We will not be generating code diagrams for this project. Instead we will focus on the Deployment Diagram, which will map our current platform to the physical cloud architecture, which will help us visualize better the high level architectural changes.

**Tools**: This document utilizes [C4 Diagrams](https://c4model.com/) and (Markdown files)[https://www.markdownguide.org/] to generate all the pages using (VSCode)[https://code.visualstudio.com/], the (PlantUML plugin)[https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml] and the (nodejs c4builder project)[https://adrianvlupu.github.io/C4-Builder/#/].


## 1 System Context Diagram

`\1 System Context Diagram`

[Overview: Running App](#Architecture-Project-#1)

![diagram](system.svg)

**Level 1: System Context**

The system context diagram represents a high-level overview of the interactions of the main components of the current architecture.

**Primary Elements**

There are currently one main user and two main components on this application. The primary elements are as follow:

- Our main users are runners that want to track and improve their running habits. These persons range from teens to seniors of all genders. 

- The first main component is the mobile application, designed to allow users to select a running program, track their runs with GPS data , count calories of each run , and enhance the running experience with a music playlist. 

- The second main component is a web dashboard that is designed to give users an overview of their runs and track their progress over time. They can also manage their accounts and purchase advanced plans with live trainer support.


**Secondary Elements**

- Trainers are professional runners that provide services guiding our runners into their journey.

## Container Diagram

`\1 System Context Diagram\Container Diagram`

[Overview: Running App](#Architecture-Project-#1)

![diagram](container.svg)

**Level 2: Container diagram**

<!-- We now start to break down each individual part of the overview context into containers. -->

Each part of our application is a two tier app, which means we have a code layer for presentation and one for business logic. The presentation layer on mobile is coded on native code and fetches data from the API via RESTful calls. 

The same pattern is observed with our Web Dashboard application, which retrieve data from the API layer and serve the HTML pages to the clients. 

<!-- Once you understand how your system fits in to the overall IT environment, a really useful next step is to zoom-in to the system boundary with a Container diagram. A "container" is something like a server-side web application, single-page application, desktop application, mobile app, database schema, file system, etc. Essentially, a container is a separately runnable/deployable unit (e.g. a separate process space) that executes code or stores data.

The Container diagram shows the high-level shape of the software architecture and how responsibilities are distributed across it. It also shows the major technology choices and how the containers communicate with one another. It's a simple, high-level technology focussed diagram that is useful for software developers and support/operations staff alike. -->


## API App Component

`\1 System Context Diagram\Container Diagram\API App Component`

[Overview: Running App](#Architecture-Project-#1)

![diagram](container.svg)

**Level 3: Component diagram**

The API layer supports the following RESTful endpoints over HTTPS:

For the mobile app
- /login
- /logout
- /getRunTypes
- /startRun
- /stopRun
- /estimatedCaloryBurned
- /addUserInfo

For the web dashboard:

- /manageAccount
- /getHistoryData
- /viewPlans
- /upgradePlan
- /cancelPlan
- /bookTrainer
- /cancelBooking


<!-- Next you can zoom in and decompose each container further to identify the major structural building blocks and their interactions.

The Component diagram shows how a container is made up of a number of "components", what each of those components are, their responsibilities and the technology/implementation details.

**Scope**: A single container.

**Primary elements**: Components within the container in scope.
Supporting elements: Containers (within the software system in scope) plus people and software systems directly connected to the components.

**Intended audience**: Software architects and developers. -->

## Mobile App Component

`\1 System Context Diagram\Container Diagram\Mobile App Component`

[Overview: Running App](#Architecture-Project-#1)

![diagram](container.svg)

**Level 3: Component diagram**

<!-- Next you can zoom in and decompose each container further to identify the major structural building blocks and their interactions.

The Component diagram shows how a container is made up of a number of "components", what each of those components are, their responsibilities and the technology/implementation details.

**Scope**: A single container.

**Primary elements**: Components within the container in scope.
Supporting elements: Containers (within the software system in scope) plus people and software systems directly connected to the components.

**Intended audience**: Software architects and developers.

> Example of included local image

![](2020-01-10-16-21-41.png) -->

## Web App Component

`\1 System Context Diagram\Container Diagram\Web App Component`

[Overview: Running App](#Architecture-Project-#1)

![diagram](container.svg)

**Level 3: Component diagram**

The current Web Application is written in Java and queries all data from a single MySQL instance. 

This is slowing our application since all reads are competing with the writes.  

<!-- Next you can zoom in and decompose each container further to identify the major structural building blocks and their interactions.

The Component diagram shows how a container is made up of a number of "components", what each of those components are, their responsibilities and the technology/implementation details.

**Scope**: A single container.

**Primary elements**: Components within the container in scope.
Supporting elements: Containers (within the software system in scope) plus people and software systems directly connected to the components.

**Intended audience**: Software architects and developers.

> Example of included local image

![](2020-01-10-16-21-41.png) -->

## 2 Current Deployment Diagram

`\2 Current Deployment Diagram`

[Overview: Running App](#Architecture-Project-#1)

![diagram](deployment.svg)

**Deployment diagram**

This section we view how containers in the static model are mapped to infrastructure. 

Currently we have the mobile app installed on the client directly fetching data from the API server. The installation files are served to the users phone by the respective platform marketplaces.

Our web server is already on Azure cloud, and its deployed on a single large scale VM using a web server. The code also fetches data from the API layer. 

The API layer is on a second large VM instance. 

This layer reads and writes all data from a single instance MySQL server. 

The Database is a single MySQL database and is managed by our cloud services provider. 

<!-- A deployment diagram allows you to illustrate how containers in the static model are mapped to infrastructure. This deployment diagram is based upon a UML deployment diagram, although simplified slightly to show the mapping between containers and deployment nodes. A deployment node is something like physical infrastructure (e.g. a physical server or device), virtualised infrastructure (e.g. IaaS, PaaS, a virtual machine), containerised infrastructure (e.g. a Docker container), an execution environment (e.g. a database server, Java EE web/application server, Microsoft IIS), etc. Deployment nodes can be nested.

**Scope**: A single software system.

**Primary elements**: Deployment nodes and containers within the software system in scope.

**Intended audience**: Technical people inside and outside of the software development team; including software architects, developers and operations/support staff. -->

## 3 One Month Plan

`\3 One Month Plan`

[Overview: Running App](#Architecture-Project-#1)

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

## 4 Long Term Plan

`\4 Long Term Plan`

[Overview: Running App](#Architecture-Project-#1)

![diagram](deployment.svg)

**Deployment diagram**

This section we view how containers in the static model are mapped to infrastructure. 

Currently we have the mobile app installed on the client directly fetching data from the API server. The installation files are served to the users phone by the respective platform marketplaces.

Our web server is already on Azure cloud, and its deployed on a single VM using IIS as a web server. The code also fetches data from the API layer. 

The API layer reads and writes all data from a single instance MySQL server. 

A deployment diagram allows you to illustrate how containers in the static model are mapped to infrastructure. This deployment diagram is based upon a UML deployment diagram, although simplified slightly to show the mapping between containers and deployment nodes. A deployment node is something like physical infrastructure (e.g. a physical server or device), virtualised infrastructure (e.g. IaaS, PaaS, a virtual machine), containerised infrastructure (e.g. a Docker container), an execution environment (e.g. a database server, Java EE web/application server, Microsoft IIS), etc. Deployment nodes can be nested.

**Scope**: A single software system.

**Primary elements**: Deployment nodes and containers within the software system in scope.

**Intended audience**: Technical people inside and outside of the software development team; including software architects, developers and operations/support staff.