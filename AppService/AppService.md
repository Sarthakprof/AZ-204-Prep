# AppService Notes

#About:
1. Azure App Service is an HTTP-based service for hosting web applications, REST APIs, and mobile back ends.
2. You can develop in your favorite language, be it .NET, .NET Core, Java, Ruby, Node.js, PHP, or Python.
3. Applications run and scale with ease on both Windows and Linux-based environments.
4. Adds power of security, load balancing, autoscaling, and automated management.
5. Has DevOps capability such as continuous deployment from Azure DevOps, GitHub, Docker Hub, and other sources, package management, staging environments, custom domain, and TLS/SSL certificates.
6. With App Service, you pay for the Azure compute resources you use. The compute resources you use are determined by the App Service plan that you run your apps on.

#Features:
1. Multiple languages and frameworks - App Service has first-class support for ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP, or Python. You can also run PowerShell and other scripts or executables as background services.
2. Managed production environment - App Service automatically patches and maintains the OS and language frameworks for you. Spend time writing great apps and let Azure worry about the platform.
3. Containerization and Docker - Dockerize your app and host a custom Windows or Linux container in App Service. Run multi-container apps with Docker Compose. Migrate your Docker skills directly to App Service.
4. DevOps optimization - Set up continuous integration and deployment with Azure DevOps, GitHub, BitBucket, Docker Hub, or Azure Container Registry. Promote updates through test and staging environments. Manage your apps in App Service by using Azure PowerShell or the cross-platform command-line interface (CLI).
5. Global scale with high availability - Scale up or out manually or automatically. Host your apps anywhere in Microsoft's global datacenter infrastructure, and the App Service SLA promises high availability.
6. Connections to SaaS platforms and on-premises data - Choose from more than 50 connectors for enterprise systems (such as SAP), SaaS services (such as Salesforce), and internet services (such as Facebook). Access on-premises data using Hybrid Connections and Azure Virtual Networks.
7. Security and compliance - App Service is ISO, SOC, and PCI compliant. Authenticate users with Azure Active Directory, Google, Facebook, Twitter, or Microsoft account. Create IP address restrictions and manage service identities.
8. Application templates - Choose from an extensive list of application templates in the Azure Marketplace, such as WordPress, Joomla, and Drupal.
9. Visual Studio and Visual Studio Code integration - Dedicated tools in Visual Studio and Visual Studio Code streamline the work of creating, deploying, and debugging.
10. API and mobile features - App Service provides turn-key CORS support for RESTful API scenarios, and simplifies mobile app scenarios by enabling authentication, offline data sync, push notifications, and more.
11. Serverless code - Run a code snippet or script on-demand without having to explicitly provision or manage infrastructure, and pay only for the compute time your code actually uses (see Azure Functions).

#Limitations
1. App Service on Linux is not supported on Shared pricing tier.
2. You can't mix Windows and Linux apps in the same App Service plan.
Historically, you can't mix Windows and Linux apps in the same resource group. However, all resource groups created on or after January 21, 2021 do support this scenario. For resource groups created before January 21, 2021, the ability to add mixed platform deployments will be rolled out across Azure regions (including National cloud regions) soon.
3. The Azure portal shows only features that currently work for Linux apps. As features are enabled, they're activated on the portal.
4. When deployed to built-in images, your code and content are allocated a storage volume for web content, backed by Azure Storage. The disk latency of this volume is higher and more variable than the latency of the container filesystem. Apps that require heavy read-only access to content files may benefit from the custom container option, which places files in the container filesystem instead of on the content volume.

#Deployement Slots
Using the Azure portal, you can easily add deployment slots to an App Service web app. For instance, you can create a staging deployment slot where you can push your code to test on Azure. Once you are happy with your code, you can easily swap the staging deployment slot with the production slot. You do all this with a few simple mouse clicks in the Azure portal.

#Continuous integration/deployment support
1. The Azure portal provides out-of-the-box continuous integration and deployment with Azure DevOps, GitHub, Bitbucket, FTP, or a local Git repository on your development machine.
2. Connect your web app with any of the above sources and App Service will do the rest for you by automatically syncing your code and any future changes on the code into the web app.
3. Furthermore, with Azure DevOps, you can define your own build and release process that compiles your source code, runs the tests, builds a release, and finally deploys the release into your web app every time you commit the code. 

#Integrated Visual Studio publishing and FTP publishing
1. Tight integration with Visual Studio to publish your web app to Azure via Web Deploy technology. 
2. App Service also supports FTP-based publishing for more traditional workflows.

#Built-in auto scale support (automatic scale-out based on real-world load)
1. Baked into the web app is the ability to scale up/down or scale out. 
2. Depending on the usage of the web app, you can scale your app up/down by increasing/decreasing the resources of the underlying machine that is hosting your web app.
3. Resources can be number of cores or the amount of RAM available.
4. Scaling out, on the other hand, is the ability to increase the number of machine instances that are running your web app.

#Operating Systems
1. If you are deploying your app as code, many of the available runtime stacks are limited to one operating system or the other.
2. After choosing a runtime stack, the toggle will indicate whether or not you have a choice of operating system. If your target runtime stack is available on both operating systems, select the one that you use to develop and test your application.
3. If your application is packaged as a Docker image, choose the operating system on which your image is designed to run.
4. Selecting Windows activates the Monitoring tab, where you have the option to enable Application Insights. Enabling this feature will configure your app to automatically send detailed performance telemetry to the Application Insights monitoring service without requiring any changes to your code. Application Insights can be used from Linux-hosted apps as well, but this turnkey, no-code option is only available on Windows.

#App Service plans
1. An App Service plan is a set of virtual server resources that run App Service apps.
2. A plan's size (sometimes referred to as its sku or pricing tier) determines the performance characteristics of the virtual servers that run the apps assigned to the plan and the App Service features that those apps have access to.
3. Every App Service web app you create must be assigned to a single App Service plan that runs it.
4. A single App Service plan can host multiple App Service web apps. In most cases, the number of apps you can run on a single plan will be limited by the performance characteristics of the apps and the resource limitations of the plan.
5. App Service plans are the unit of billing for App Service. The size of each App Service plan in your subscription, in addition to the bandwidth resources used by the apps deployed to those plans, determines the price that you pay. The number of web apps deployed to your App Service plans has no effect on your bill.
6. You can use any of the available Azure management tools to create an App Service plan. When you create a web app via the Azure portal, the wizard will help you to create a new plan at the same time if you don't already have one.

#Automated deployment
Automated deployment, or continuous integration, is a process used to push out new features and bug fixes in a fast and repetitive pattern with minimal impact on end users.

Azure supports automated deployment directly from several sources. The following options are available:

1. Azure DevOps: You can push your code to Azure DevOps (previously known as Visual Studio Team Services), build your code in the cloud, run the tests, generate a release from the code, and finally, push your code to an Azure Web App.
2. GitHub: Azure supports automated deployment directly from GitHub. When you connect your GitHub repository to Azure for automated deployment, any changes you push to your production branch on GitHub will be automatically deployed for you.
3. Bitbucket: With its similarities to GitHub, you can configure an automated deployment with Bitbucket.
4. OneDrive: Microsoft's cloud-based storage. You must have a Microsoft Account linked to a OneDrive account to deploy to Azure.
5. Dropbox: Azure supports deployment from Dropbox, which is a popular cloud-based storage system that is similar to OneDrive.

#Manual deployment
There are a few options that you can use to manually push your code to Azure:

1. Git: App Service web apps feature a Git URL that you can add as a remote repository. Pushing to the remote repository will deploy your app.
2. az webapp up: webapp up is a feature of the az command-line interface that packages your app and deploys it. Unlike other deployment methods, az webapp up can create a new App Service web app for you if you haven't already created one.
3. ZIP deploy: Use az webapp deployment source config-zip to send a ZIP of your application files to App Service. ZIP deploy can also be accessed via basic HTTP utilities such as curl.
4. WAR deploy: It's an App Service deployment mechanism specifically designed for deploying Java web applications using WAR packages. WAR deploy can be accessed using the Kudu HTTP API located at http://<your-app-name>.scm.azurewebsites.net/api/wardeploy. If this fails try: https://<your-app-name>.scm.azurewebsites.net/api/wardeploy.
5. Visual Studio: Visual Studio features an App Service deployment wizard that can walk you through the deployment process.
6. FTP/S: FTP or FTPS is a traditional way of pushing your code to many hosting environments, including App Service.

#App Service plans and scalability
1. A web app running in Azure typically uses Azure App Service to provide the hosting environment.
2.  App Service can arrange for multiple instances of the web app to run and will load balance incoming requests across these instances. 
3. Each instance runs on a virtual machine.
4. The resources available to each instance are defined by an App Service plan.
5. The App Service plan specifies the operating system (Windows or Linux), the hardware (memory, CPU processing capacity, disk storage, and so on), and the availability of services like automatic backup and restore.

Azure provides a series of well-defined App Service plan tiers. This list summarizes each of these tiers, in increasing order of capacity (and cost):

1. The Free tier provides 1 GB of disk space and support for up to 10 apps, but only a single shared instance and no SLA for availability. Each app has a compute quota of 60 minutes per day. The Free service plan is mainly suitable for app development and testing rather than production deployments.
2. The Shared tier provides support for more apps (up to 100) also running on a single shared instance. Apps have a compute quota of 240 minutes per day. There is no availability SLA.
3. The Basic tier supports an unlimited number of apps and provides more disk space. Apps can be scaled out to three dedicated instances. This tier provides an SLA of 99.95% availability. There are three levels in this tier that offer varying amounts of computing power, memory, and disk storage.
4. The Standard tier also supports an unlimited number of apps. This tier can scale to 10 dedicated instances and has an availability SLA of 99.95%. Like the Basic tier, this tier has three levels that offer an increasingly powerful set of computing, memory, and disk options.
5. The Premium tier gives you up to 20 dedicated instances, an availability SLA of 99.95%, and multiple levels of hardware.
6. The Isolated tier runs in a dedicated Azure virtual network, which gives you a network and computes isolation. This tier can scale out to 100 instances and has an availability SLA of 99.95%.