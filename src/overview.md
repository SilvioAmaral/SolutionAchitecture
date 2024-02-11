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
