## Before you install .NET, run the following commands to add the Microsoft package signing key to your list of trusted keys and add the Microsoft package repository. Open a terminal and run the following commands:
```
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
sudo yum install dotnet-sdk-5.0
sudo yum install aspnetcore-runtime-5.0
dotnet tool install -g Amazon.Lambda.Tools
dotnet tool install --global Amazon.Lambda.TestTool-3.1
```
