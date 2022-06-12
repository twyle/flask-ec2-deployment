# flask-ec2-deployment
> This is a simple flask application that shows how to deploy a production grade application to AWS EC2.

[![Feature Development Build](https://github.com/twyle/flask-ec2-deployment/actions/workflows/feature-development-workflow.yml/badge.svg)](https://github.com/twyle/flask-ec2-deployment/actions/workflows/feature-development-workflow.yml)
[![Development Build](https://github.com/twyle/flask-ec2-deployment/actions/workflows/development-workflow.yml/badge.svg)](https://github.com/twyle/flask-ec2-deployment/actions/workflows/development-workflow.yml)
[![security: bandit][bandit-image]][bandit-url]
[![Imports: isort][isort-image]][isort-url]
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)
[![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)
![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white)
![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Gunicorn](https://img.shields.io/badge/gunicorn-%298729.svg?style=for-the-badge&logo=gunicorn&logoColor=white)

![](flask-ec2-cover.png)


This project shows how to lauch a production grade application to AWS EC2. It is a simple flask application, with the following features:
- ***A User Registration System.***
- ***A User Authentication and Authorization System.***
- ***A User Creation System.***
- ***Uses the PostgresQL Database to store both users as well as authentication and authorization information.***
- ***A logging system that logs to file and sends emails on critical errors.***
- ***It is deployed to an AWS EC2 instance with gunicorn server and nginx as a proxy.***

If you want to learn more about how it was developed, read ***[How to Deploy a Production Grade Flask application to an AWS EC2 Instance using GitHub Actions](https://medium.com/@lyle-okoth/how-to-deploy-a-production-grade-flask-application-to-an-aws-ec2-instance-using-github-actions-6241886b197)***. The are atleast five branches associated with the application:

- **Features** - Used to create new features
- **Development** - Where all the newly developed features are showcased
- **Staging** - Used to test out the nwely developed features before being moved to production
- **Release** - Holds all the code and assets related to the latest release
- **Production** - Holds all the code that is currentlyin production.

The development workflow is pretty straight forward:

- A new feature branch is created, to host the code for the new feature.
- When this is pushed to GitHub, it triggers a workflow that does code quality checks as well as run unit tests, then tests that the application does run.
- When the feature branch is merged into the development branch, the same code quality checks are run. In addition , the code is pushed to the development server and then the application is restarted with the changes.
- The development branch is merged into the staging branch, following the same workflow, but the code is autodeployed to a staging server.
- When a tag is pushed to GitHub, the staging branch is merged into the Release branch and a release is created.
- When the rellease branch is merged into the production branch, the code is pushed to the production server and the production application restarted with the changes.

<!-- Markdown link & img dfn's -->
[wiki]: https://github.com/yourname/yourproject/wiki

[bandit-image]: https://img.shields.io/badge/security-bandit-yellow.svg
[bandit-url]: https://github.com/PyCQA/bandit

[isort-image]: https://img.shields.io/badge/%20imports-isort-%231674b1?style=flat&labelColor=ef8336
[isort-url]: https://pycqa.github.io/isort/
