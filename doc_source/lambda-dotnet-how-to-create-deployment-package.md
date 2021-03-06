# Creating a Deployment Package \(C\#\)<a name="lambda-dotnet-how-to-create-deployment-package"></a>

A \.NET Core Lambda deployment package is a zip file of your function's compiled assembly along with all of its assembly dependencies\. The package also contains a `proj.deps.json` file\. This signals to the \.NET Core runtime all of your function's dependencies and a `proj.runtimeconfig.json` file, which is used to configure the \.NET Core runtime\. The \.NET CLI’s `publish` command can create a folder with all of these files, but by default the `proj.runtimeconfig.json` will not be included because a Lambda project is typically configured to be a class library\. To force the `proj.runtimeconfig.json` to be written as part of the `publish` process, pass in the command line argument: `/p:GenerateRuntimeConfigurationFiles=true to the publish command`\. 

**Note**  
Although it is possible to create the deployment package with the `dotnet publish` command, we suggest you create the deployment package with either the [AWS Toolkit for Visual Studio](lambda-dotnet-create-deployment-package-toolkit.md) or the [\.NET Core CLI](lambda-dotnet-coreclr-deployment-package.md)\. These are tools optimized specifically for Lambda to ensure the `lambda-project.runtimeconfig.json` file exists and optimizes the package bundle, including the removal of any non\-Linux\-based dependencies\. 

**Topics**
+ [\.NET Core CLI](lambda-dotnet-coreclr-deployment-package.md)
+ [AWS Toolkit for Visual Studio](lambda-dotnet-create-deployment-package-toolkit.md)