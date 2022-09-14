---
title: Strapi Cloud Deployment - Strapi Developer Docs
description: Learn how to deploy your Strapi application on Strapi Cloud.
canonicalUrl: https://docs.strapi.io/developer-docs/latest/setup-deployment-guides/deployment/strapi-cloud.html
---

# Strapi Cloud

::: warning
Strapi Cloud is currently in Closed Beta release. Features and functionality may change prior to General Availability.
:::

This is a step-by-step guide for deploying your Strapi application on Strapi Cloud.

## Prerequisites

Before you can deploy your Strapi application on Strapi Cloud, you need to have the following prerequisites:

* A [GitHub](https://github.com) account
* GitHub repository for each Strapi application to be deployed

::: tip
Each Strapi app must be in a separate repository. Your Strapi Cloud account can link to multiple repositories to deploy multiple apps, if needed.
:::

## Getting started

1. Navigate to the [Strapi Cloud](https://cloud.strapi.io) login page.

![Strapi Cloud login page](../assets/deployment/cloud/login.png)

2. You are prompted to **Log In with GitHub**. Your Strapi Cloud account is created during this initial login.

3. Once logged in, you will be redirected to the Strapi Cloud **Projects** page. From here you can create your first Strapi Cloud project.

![Strapi Cloud Projects page](../assets/deployment/cloud/projects_empty.png)

### Create a project

1. From the **Projects** page, click the **Create Project** button. You are prompted to **Connect with GitHub**.

::: tip
Connect the GitHub account that owns the repository or repositories you want to deploy. This can be different from the account that owns the Strapi Cloud account.

You will be redirected to GitHub to authorize Strapi Cloud to access your repository.
:::

2. After granting the required access form GitHub, from the **Projects** page select your desired repository to install Strapi Cloud.

![Project Import - Select Repository](../assets/deployment/cloud/import.png)

3. Click **Next** to proceed to the Project Set up page and enter the following information:

![Project Setup](../assets/deployment/cloud/setup.png)
    * **Project name**: The name of your Strapi app, this is fetched from the repository name but can be edited. It is automatically converted to slug format (`my-strapi-app`).
    * **GitHub branch**: The default branch to use for this deployment. This uses the [default branch](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/changing-the-default-branch) of the repository but can be changed via the drop-down.
    * Deploy on push: When enabled, this will automatically deploy the latest changes from the selected branch. When disabled, you will need to manually deploy the latest changes.

4. (**Optional**) Select **Show Advanced Settings** to configure the following options:

![Advanced Setup](../assets/deployment/cloud/advanced.png)
    * [**Environment variables**](../configurations/optional/environment.md): Environment variables are used to configure your Strapi app.
    * **Base directory**: The directory where your Strapi app is located in the repository. This is useful if you have multiple Strapi apps in the same repository.

5. Click **Create** to finalize the project creation. An initial deployment is triggered and you are redirected to the **Projects** page.

## Managing projects

The **Projects** page displays a list of all your Strapi Cloud projects. From here you can manage your projects and access the corresponding applications.

![Projects page - List](../assets/deployment/cloud/project_list.png)

Each project card displays the following information:

* Project name
* Status: Displays a **Disconnected** warning if the project repository is not connected to Strapi Cloud.
* Last deployment date: Timestamp of the last deployment.

## Project details

From the **Projects** page, click on any project card to access that project's details page.

The project details page displays the following tabs: **Deploys** and **Settings**.

### Deploys

The **Deploys** tab displays a chronological list of cards with the details of all historical deployments for the project.

![Project deploys](../assets/deployment/cloud/deploys.png)

Each card displays the following information:

* Commit SHA
* Commit message
* Deployment status: Whether the project is **Deploying**, the **Build failed**, or the deployment is **Done**.
* Last deployment time: When the deployment was triggered and the duration.
* Production branch
* Options menu (`...`): The available options vary depending on the deployment status.
    * For **Done** status: No further options.
    * For **Deploying** status, you can:
        * **Cancel deploy**
    * For **Build failed** status, you can:
        * **Download error logs**

From this page you can also trigger a new deployment and access the application using the corresponding buttons.

## Settings

The **Settings** enables you to edit the following details for the project:

![Project settings](../assets/deployment/cloud/settings.png)

* Project name
* Production branch
* Environment variables
* Connected GitHub repository