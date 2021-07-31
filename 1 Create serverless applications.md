# Create serverless applications

Azure Functions enable the creation of event driven, compute-on-demand systems that can be triggered by various external events. 

Learn how to leverage functions to execute server-side logic and build serverless architectures. Total: 10 Modules

## 1. Choose the best Aure service to automate your business processes

Microsoft Azure provides several different ways to host and execute code or workflows without using Virtual Machines (VMs) including Azure Functions, Microsoft Power Automate, Azure Logic Apps, and Azure WebJobs. 

### 1.1 Identify the technology options
- Common business issues
- Design-first technologies
- Code-first technologies
### 1.2 Analyze the decision criteria
- How to choose a service

  Azure includes the following technologies that you can use to overcome these challenges:
  1. Microsoft Power Automate
  2. Azure Logic Apps
  3. Azure Functions
  4. Azure App Service WebJobs

  Your choice of technology depends on whether you prefer a design-first or a code-first approach, 
  and whether you have skilled developers to work on the project.

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

- **Scenario 2 - Camera Company Merger**

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

  Benefits of a serverless compute solution
  Stateless logic
  Event driven
  Functions can be used in traditional compute environments

-  Drawbacks of a serverless compute solution

  Execution time
  Execution frequency

### 2.2 Exercise - Create a function app in the Azure portal
- What is a function app?
- Create a function app
- Verify your Azure function app

### 2.3 Run your code on-demand with Azure Functions
- Triggers

Functions are event driven, which means they run in response to an event.

The type of event that starts the function is called a trigger. You must configure a function with exactly one trigger.
- Bindings

  Bindings are a declarative way to connect data and services to your function. 
  Bindings know how to talk to different services, which means you don't have to 
  write code in your function to connect to data sources and manage connections. 
  The platform takes care of that complexity for you as part of the binding code. 
  Each binding has a direction - your code reads data from input bindings, 
  and writes data to output bindings. Each function can have zero or more bindings to
  manage the input and output data processed by the function.

  A trigger is a special type of input binding that has the additional capability of initiating execution.

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
### 3.1 Determine the best trigger for your Azure function
- What is a trigger? A trigger is an object that defines how an Azure Function is invoked. For example, if you want a function to execute every 10 minutes, you could use a timer trigger.Here  focus on three trigger types: timer, HTTP, and blob.
- Types of triggers, Azure Functions support a wide range of trigger types. Here are some of the most common types:
- What is a binding? A binding is a connection to data within your function. Bindings are optional and can be input bindings, output bindings, or both. An input binding is the data that your function receives. An output binding is the data that your function sends. Unlike a trigger, a function can have multiple input bindings and output bindings.
### 3.2 Run an Azure Function on a schedule
- What is a timer trigger? A timer trigger is a trigger that executes a function at a consistent interval. To create a timer trigger, you need to supply two pieces of information. 1. A Timestamp parameter name, which is simply an identifier to access the trigger in code. 2. A Schedule, which is a CRON expression that sets the interval for the timer.
- What is a CRON expression?A CRON expression is a string that consists of six fields that represent a set of times.

The order of the six fields in Azure is: {second} {minute} {hour} {day} {month} {day of the week}.
- How to create a timer trigger: You can create a timer trigger in the Azure portal. In your Azure function app, select timer trigger from the list of trigger templates. Enter the logic that you want to execute. Supply a Timestamp parameter name and the CRON expression.
### 3.3 Exercise - Create a timer trigger
- Create an Azure Function App
- Create a timer-triggered function
- Configure the timer trigger
- Test the timer
### 3.4 Execute an Azure function with an HTTP request
- What is an HTTP trigger? An HTTP trigger is a trigger that executes a function when it receives an HTTP request.
- What is an HTTP trigger Authorization level? An HTTP trigger Authorization level is a flag that indicates whether an incoming HTTP request needs an API key for authentication.

There are three Authorization levels: Function, Anonymous, Admin
- How to create an HTTP trigger: Just like a timer trigger, you can create an HTTP trigger through the Azure portal. Inside your Azure function, select HTTP trigger from the list of predefined trigger types, then enter the logic that you want to execute and make any customizations, like restricting the use of certain HTTP verbs.
- How to invoke an HTTP trigger? To invoke an HTTP trigger, you send an HTTP request to the URL for your function. To get this URL, go to the code page for your function and select the Get function URL link.
### 3.5 Exercise - Create an HTTP trigger
- Create an HTTP trigger
- Get your function URL
- Issue a GET request to your HTTP trigger
### 3.6 Execute an Azure function when a blob is created
- What is Azure Storage? Azure Storage is Microsoft's cloud storage solution that supports all types of data, including: blobs, queues, and NoSQL.
- What is Azure Blob storage? Azure Blob storage is an object storage solution that's designed to store large amounts of unstructured data.
- What is a blob trigger? A blob trigger is a trigger that executes a function when a file is uploaded or updated in Azure Blob storage. To create a blob trigger, you create an Azure Storage account and provide a location that the trigger monitors.
- How to create a blob trigger? Just like the other triggers we've seen so far, you create a blob trigger in the Azure portal. Inside your Azure function, select Blob trigger from the list of predefined trigger types. Then, you enter the logic to that you want to execute when a blob is created or updated.
### 3.7 Exercise - Create a Blob trigger
- Create a blob trigger
- Create a blob container
- Turn on your blob trigger
- Create a blob
### 3.8 Knowledge check
1. A CRON expression is a string that consists of six fields that represent a set of times. The order of the six fields in Azure is: {second} {minute} {hour} {day} {month} {day of the week}. Suppose you needed a CRON expression that meant "every day", what special character would you put in the {day of the week} position?
```
** * **
An asterisk specifies that every possible value should be selected. 
Having an asterisk in the {day of the week} field means that every day should be selected.
```
2. Suppose your Azure Function has a blob trigger associated with it and you want it to execute only when png images are uploaded. Which of the following blob trigger Path values should you use?
```
**samples-workitems/{name}.png**
The Path tells the blob trigger where it should monitor for changes, and if there are any filters applied. 
Adding a file extension to the Path specifies that uploaded files must have 
that file extension in order for the trigger to invoke the function.
```
3. True or false: an Azure Function can have multiple triggers associated with it?
```
**False**
Every Azure Function must have exactly one trigger associated with it. 
If you want to use multiple triggers, you must create multiple functions.
```
## 4. Chain Azure functions together using input and output bindings

## 5. Create a long-running serverless workflow with Durable Functions

## 6. Develop,test,and publish Azure Functions by using Azure Functions Core Tools

## 7. Develop,test,and deploy an Azure Function with Visual Studio

## 8. Monitor GitHub events by using a webhook with Azure Functions

## 9. Enable automatic updates in a web application using Azure Functions and SignalR Service

## 10. Expose multiple Azure Function apps as a consistent API by using Azure API Management
