# Visualizer
Aplicación para buscar contenidos de Enron Corp DB

## To Deploy this project in AWS Elastic Beanstalk:

1. Install EB CLI: https://docs.aws.amazon.com/es_es/elasticbeanstalk/latest/dg/eb-cli3-install-osx.html

2. At /Visualizer execute in terminal eb init and follow the steps
    - region us-east-1
    - Select an application or create one
    - Select a platform (Go)
    - Select a platform branch
    - Continue with CodeCommit?: n
    - Set ssh?: n

3. Execute eb create and follow the steps
    - Environment Name
    - DNS CNAME prefix
    - Load balancer type: classic 
    - Enable Spot Fleet request?: n

4. At root in /Visualizer add a file named .ebignore and paste this: !application

5. Compile the Vue App and then at /Visualizer execute: GOOS=linux GOARCH=amd64  go build -o bin/application

6. Execute: eb deploy

7. For add an environment variable execute: eb setenv NAME=value
