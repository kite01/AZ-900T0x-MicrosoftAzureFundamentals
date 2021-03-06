---
wts:
    title: '22 - Calculate Composite SLAs'
    module: 'Module 04 - Azure Pricing and Support'
---
# 22 - Calculate Composite SLAs


In this walkthrough, we will determine services SLA uptime percentages and then calculate the application composite SLA uptime percentage.

Estimated time: 15 minutes

Our example application consists of these Azure services. We will not go in to deep architectural configuration and considerations, the intention here is to give an high level example.

+ **App service**: To host the application.
+ **Azure AD B2C**: To authenticate user logins and manage profiles.
+ **Application Gateway**: To manage application access, scaling and scaling. 
+ **Azure SQL Database**: To store application data. 

# Task 1: Determine the SLA uptime percentage values for our application

1. In a browser, go to the [SLA summary for Azure services](https://azure.microsoft.com/en-us/support/legal/sla/summary/) page.

2. Locate the **App Service** SLA uptime value, **99.95%**. Click **View full details**, and then expand **SLA details**. Notice the **Monthly uptime percentages** and **Service Credits**.

3. Return to the SLA webpage and locate the **Azure Active Directory B2C** service and determine the SLA uptime value, **99.9%**. 

4. Locate the **Azure Application Gateway** SLA uptime value, **99.95%**. 

5. The Azure SQL database uses Premium tiers not configured for Zone Redundant Deployments. Locate the **Azure SQL Database** SLA uptime value, **99.99%**. 

    **Note**: There are different uptime values for different configurations and deployments of Azure SQL Database. It is important you are clear on your required uptime values, when planning and costing your deployment and configuration. Small changes in uptime can have impact on service costs as well as potentially increase complexity in configuration. Some other services that may be of interest to look at for examples on the Azure SLA summary web page would include **Virtual Machines**, **Storage Accounts** and **Cosmos DB**.

# Task 2: Calculate the Application Composite SLA percentage uptime

1. If any of the services that comprises our application are not available our application will not be available for users to sign in to and use. As such the total uptime for our application consists of the following:

    **App Service % uptime** X **Azure AD B2C % uptime** X  **Azure Application Gateway % uptime** X **Azure SQL Database % uptime** = **Total % Uptime**

    which in percentage term is as follows:

    **99.95%** X **99.9%** X **99.95%** X **99.99%** = **99.79%**


    This is the percentage uptime that our application will be able to achieve with the current services and architecture.

Congratulations! You have determined the SLA uptime percentages for each of the services in our sample application and then calculated the composite SLA uptime percentage for the application.

