# Software Architecture Course

**Project Part 1**

A small sized company has a running application which allows users to track their running habits and get motivated by visualizing their progress.

Unfortunately, customers have been complaining about problems and the business is losing customers to the competition. 

In this document we have devised a one month plan to tackle the three immediate pain points with an improve in our software architecture. Also , we will suggest a long term plan to have the best possible architecture available for the given requirements.

**Pain Points**

- the app is not responsive during a run, especially trying to start and stop it
- some customers mentioned that their runs are disappearing from the web dashboard
- when customers finish a run, it takes more than one day to view on the dashboard

**Primary Goals**

- make the mobile app more responsive during a run
- have better data consistency on web dashboard
- immediately view runs on dashboard after a run ends

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

**Limitations**: From the 4 suggested diagrams on C4 models, We will not be generating component and code diagrams. Instead we will create System Context and Container diagrams along with Deployment Diagrams , which will map our current platform to the physical cloud architecture, for current setup, one month attack plan and the final solution. This will help us visualize better the high level architectural changes proposed.

**Tools**: 
This document utilizes [Markdown files](https://www.markdownguide.org/) for text notes and [PlantUML](https://plantuml.com/) for diagram generations. 

The diagrams follow the [C4 Diagrams](https://c4model.com/) model of visualization. 

The text editor of choice was [VSCode](https://code.visualstudio.com/) using the [PlantUML plugin](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml) and the [NodeJS c4builder project](https://adrianvlupu.github.io/C4-Builder/#/).

**Github**:https://github.com/SilvioAmaral/SolutionAchitecture