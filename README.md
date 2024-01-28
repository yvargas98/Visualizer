# Visualizer
Aplicación para buscar contenidos de Enron Corp DB

## To Deploy this project in AWS Elastic Beanstalk:

1. Install EB CLI: https://docs.aws.amazon.com/es_es/elasticbeanstalk/latest/dg/eb-cli3-install-osx.html

2. At /Visualizer execute in terminal eb init and follow the steps
    - region us-east-1
    - Select an application or create one
    - Continue with CodeCommit?: n
    - Add ssh?: n

3. At root in /Visualizer add a file named .ebignore and paste this: !application

4. Compile the Vue App and then at /Visualizer execute: GOOS=linux GOARCH=amd64  go build -o bin/application

4. Execute: eb deploy

5. For add an environment variable execute: eb setenv NAME=value

6. This proyect isn't work because there is a problem with the Open Observe API to search content, view here https://discuss.openobserve.ai/t/-search-api-authentication-issue-in-zinc-cloud/2L3e2
