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