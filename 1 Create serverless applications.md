# Create serverless applications

Azure Functions enable the creation of event driven, compute-on-demand systems that can be triggered by various external events. 

Learn how to leverage functions to execute server-side logic and build serverless architectures. Total: 10 Modules

## 1. Choose the best Aure service to automate your business processes

Microsoft Azure provides several different ways to host and execute code or workflows without using Virtual Machines (VMs) including Azure Functions, Microsoft Power Automate, Azure Logic Apps, and Azure WebJobs. 

### 1.1 Identify the technology options
- Common business issues
  ```
  Some business processes are simple, but often they include challenges such as:

    - They might involve many different steps, sometimes with loops or conditional branches.
    - They may be long-running and complete over days or weeks as staff become available or because of other delays.
    - They may involve several different systems such as databases, web services, email servers, and other components.
    - You may want to integrate a custom or third-party system, which may require a custom connector.
    - You may want non-developers to be able to modify and update the workflow.
  ```
- Design-first technologies
- Code-first technologies
### 1.2 Analyze the decision criteria
- How to choose a service
  ```
  Azure includes the following technologies that you can use to overcome these challenges:
  1. Microsoft Power Automate
  2. Azure Logic Apps
  3. Azure Functions
  4. Azure App Service WebJobs

  Your choice of technology depends on whether you prefer a design-first or a code-first approach, 
  and whether you have skilled developers to work on the project.
  ```
- Choosing a design-first technology
- Choosing a code-first technology
- Mixing Technologies
### 1.3 Choose the best design-first technology to automate your business process
- Scenario
- Business process
- Choose a technology
- Design-first or code-first?
- Microsoft Power Automate or Azure Logic Apps?
### 1.4 When to choose Azure Functions to run your business logic
- Scenario
- Business Process
- Choose a technology
- Design-first or code-first?
- Azure Functions or Azure Apps Service WebJobs?
### 1.5 Knowledge check
- **Scenario 1 - TV Adverts**
  ```
  You work for a company that makes TV adverts. You want to formalize two business processes:

  The advert review process. 
  A completed advert is put through this editorial process to ensure that it meets the standards of taste, 
  decency, grammar, style, and legal requirements in the jurisdiction where it will be broadcast.

  The feedback collection process. A completed advert is also put through this process in which customers, the director, 
  and members of the board of directors, can give feedback.

  The advert review process should be managed by members of the creative team, because it will need to change regularly. 
  The creative team would prefer not to have to wait for a developer to become available whenever a change is needed.

  The feedback collection process calls an on-premises SharePoint server. 
  Because this server is not as reliable as a cloud-based server would be, 
  developers want to carefully control the way the workflow retries this connection, if there is a failure.
  ```
- **Scenario 2 - Camera Company Merger**
  ```
  You work for a company that makes digital cameras. The company has recently acquired a smaller company that makes lenses. 
  You want to ensure that the same procedures are in use throughout the company for the following processes:

  Lens quality control. 
  The company you acquired has a good reputation for lens reliability because of its quality control procedure. 
  You want to implement this procedure across the merged company 
  and integrate it with your parts ordering system, which includes a REST API.

  Ordering and dispatch. The company you acquired had no formal order and dispatch procedure, 
  so you want to ensure its employees use your original business procedure. 
  The ordering system has a user interface that is built as an Azure App service web app 
  but you want to manage the order and dispatch workflow as a separate project.

  You have hired a small team of developers to do the work and you prefer a design-first approach.
  ```
- **Check your Knowledge**

1. In the television advert company, which technology would you use for the advert review process?
  ```
  **Microsoft Power Automate** 

  Implement the workflow using Microsoft Power Automate because this allows the creative team, 
  who are not developers, to manage the flow.
  ```

2. In the television advert company, which technology would you use for the feedback collection process?
  ```
  **Azure App Service WebJobs**

  WebJobs are the only technology that permits developers to control retry policies.
  ```
3. In the merged camera company, which technology would you use for the lens quality control procedure?
  ```
  **Azure Logic Apps**

  Azure Logic Apps is the only one of the four technologies 
  that provides a design-first approach intended for developers.
  ```
4. In the merged camera company, which technology would you use for the ordering and dispatch procedure?
  ```
  **Azure Logic Apps**

  Azure Logic Apps is the only one of the four technologies 
  that provides a design-first approach intended for developers.
  ```
## 2. Create serverless logic with Azure Functions

Azure Functions allow developers to host business logic that can be executed without managing or provisioning infrastructure.

### 2.1 Decide if serverless computing is right for your business needs
- What is serverless compute?
- What is Azure Functions?
- Benefits of a serverless compute solution
  ```
  Benefits of a serverless compute solution
  Stateless logic
  Event driven
  Functions can be used in traditional compute environments
  ```
-  Drawbacks of a serverless compute solution
  ```
  Execution time
  Execution frequency
  ```
### 2.2 Exercise - Create a function app in the Azure portal
- What is a function app?
- Create a function app
- Verify your Azure function app

### 2.3 Run your code on-demand with Azure Functions
- Triggers

Functions are event driven, which means they run in response to an event.

The type of event that starts the function is called a trigger. You must configure a function with exactly one trigger.
- Bindings
  ```
  Bindings are a declarative way to connect data and services to your function. 
  Bindings know how to talk to different services, which means you don't have to 
  write code in your function to connect to data sources and manage connections. 
  The platform takes care of that complexity for you as part of the binding code. 
  Each binding has a direction - your code reads data from input bindings, 
  and writes data to output bindings. Each function can have zero or more bindings to
  manage the input and output data processed by the function.

  A trigger is a special type of input binding that has the additional capability of initiating execution.
  ```
- Create a function in the Azure portal
- Navigate to your function and files
- Test your Azure function
- Monitoring and Application Insights dashboard
- Streaming logs pane
### 2.4 Exercise - Add logic to the function app
- Function requirements
- Add a function to our function app
- Test the function
- Secure HTTP triggers
- Add business logic to the function
- Test our business logic
### 2.5 Knowledge check
1. Which of the following best defines serverless logic?
  ```
  **Code you write that runs on servers a cloud provider manages.**

  Serverless doesn't mean there are no servers - 
  it just means the developer doesn't have to worry about servers. 
  Instead, a cloud provider such as Azure, manages servers.
  ```
2. The container that groups functions into a logical unit for easier management, deployment, and sharing of resources is called?
  ```
  **Function app**
  A function app is a way to organize and collectively manage your functions. 
  A function app is comprised of one or more individual functions that are managed together by Azure App Service. 
  All the functions in a function app share the same pricing plan, continuous deployment, and runtime version.
  ```

3. We secured our function against unknown HTTP callers by requiring a function-specific API key be passed with each call. Which of the following fields is the name header in the HTTP requests that needs to contain this key?
  ```
  **x-functions-key**
  The API can be included in a query string variable named "code", 
  or it can be included in an x-functions-key HTTP header.
  ```
## 3. Execute an Azure Function with triggers

## 4. Chain Azure functions together using input and output bindings

## 5. Create a long-running serverless workflow with Durable Functions

## 6. Develop,test,and publish Azure Functions by using Azure Functions Core Tools

## 7. Develop,test,and deploy an Azure Function with Visual Studio

## 8. Monitor GitHub events by using a webhook with Azure Functions

## 9. Enable automatic updates in a web application using Azure Functions and SignalR Service

## 10. Expose multiple Azure Function apps as a consistent API by using Azure API Management
