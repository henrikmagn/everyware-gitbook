# A typical project

A description of a typical Everyware project, what roles are included? Who does what? This is not a must, just how a "normal" project has been for us.

### Project members

* **Infomaker members**
  * Project lead
  * Technical project lead
  * Developers
  * Devops
* **Client members**
  * Project lead
  * Developers
  * IT
  * Editorial

### Infomaker

**Project lead -** The Infomaker project lead normally is responsible for Open Content, Writer and other services around the project. The project lead should have a good understanding of all the parts of the project and be able to organize the different products and environments.

**Technical project lead -** The Infomaker tech lead is a developer, typically a senior developer with good knowledge about Everyware, Open Content and other products in the universe. The tech lead collaborates with the client in planing, standups and other meetings to get the most out of the project, the tech lead also develops the actual product.

**Developers -** One or more Infomaker developers that are active participants in the development of the project.

**Devops -** An Infomaker devops resource that is active during the project helps out with setup of different environments, some web server configuration and helps out when it's time to launch the product.

### Client

**Project lead -** The clients project lead, ideally someone from the client who can make decisions and knows their products and the goal of the project. 

**Developers -** One or more developers that are active participants in the development of the project. 

**IT -** The clients IT department is typically involved when it's time to go live, helps out with DNS.

**Editorial -** The best projects also includes editorial staff, those who will actually work with the sites when they are finished. Good for input on features and functionality throughout the project.

### Standups and meetings

At the start of a project we normally have 2 week sprints with daily standups in the morning, max 10 minutes. Before the start of the sprint we have a sprint planning meeting where Infomaker Project lead, Infomaker Tech lead, client Project lead and client Lead developer are present.

When the sprint has ended we finish it with a meeting where everyone is present and developers demo the resolved issues for the group. If a issue is approved all is well, if more work is needed the issue is reopened.

### Version control

Git is used, during development we typically use a dev branch for most of the development. If a bigger feature is developed create a feature branch for that feature. 

Later in project and after go live of the public sites the master branch is the production environment, we deploy via tags on the master branch. Feature branches is used for all changes at this stage, branch from master and merge in to the test or stage branch to test in AWS environments.

### Environments and deploys

Every developer has their own development environment, in AWS we have a test, stage and production environment. Not all customers feel the need for a test environment and just have stage and production. 

The production environment is not set up at the beginning of the project, when the projects nears completion it is set up and made ready for deploy.

