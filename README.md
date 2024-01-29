# Visualizer: Enron Corp DB Content Searcher
Visualizer es una aplicación que permite explorar los contenidos del Enron Corp DB, un conjunto de datos públicos que contiene correos electrónicos de la empresa Enron.

## Description

Visualizer is an application that allows you to explore and analyze the contents of the Enron Corp DB, a public dataset that contains emails, calendars, and other documents from the Enron Corporation.

## Deployment on AWS Elastic Beanstalk

**Prerequisites:**

* Active AWS account
* EB CLI installed: https://docs.aws.amazon.com/es_es/elasticbeanstalk/latest/dg/eb-cli3-install-osx.html

**Step 1: Initialize the environment:**

1. In the project root, run the `eb init` command:
    * Select the region `us-east-1`.
    * Create or select an application.
    * Choose the platform `Go`.
    * Select a platform branch.
    * Respond `n` to the questions about CodeCommit and SSH.

**Step 2: Create the environment:**

1. Run the `eb create` command:
    * Assign a name to the environment.
    * Select a CNAME prefix.
    * Choose the load balancer type `classic`.
    * Respond `n` to the question about Spot Fleet.

**Step 3: Configure the deployment:**

1. Create a file named `.ebignore` in the project root and add the following line:
    ```
    !application
    ```

**Step 4: Compile the application:**

1. Compile the Vue app (if necessary).
2. In the project root, run:
    ```bash
    GOOS=linux GOARCH=amd64 go build -o bin/application
    ```

**Step 5: Deploy:**

1. Run the `eb deploy` command to deploy the application to Elastic Beanstalk.

**Step 6: Configure environment variables (optional):**

1. To add environment variables, run:
    ```bash
    eb setenv NAME=value
    

## Accessing the application

Once the deployment is complete, the application will be available at the URL provided by Elastic Beanstalk.
