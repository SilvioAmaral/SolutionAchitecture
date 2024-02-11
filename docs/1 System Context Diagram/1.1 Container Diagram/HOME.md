# 1.1 Container Diagram

![diagram](container.svg)

**Level 2: Container diagram**

Each part of our application is a two tier app, which means we have a code layer for presentation and one for business logic. Code quality is lower because of this, but this problem will be handled at a separate moment.

The presentation layer on mobile is coded on react native. The presentation layer on web is a single page application SPA on React/HTML/CSS and delivered via a web server to the client. Both presentation layers communicate to the API using JSON via RESTful calls over HTTPS. 

