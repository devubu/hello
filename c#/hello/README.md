## Compile and Run the C# Program
    dotnet build -o bin
    dotnet run --project ~/Code/hello/c#/hello

## Create a C# project (C# Console Application)
    dotnet new console -o example
    cd example

## Replace the Default Code in Program.cs
    vim Program.cs
    
## Compile the C# program into the bin directory
    dotnet build -o bin

## Run the compiled C# program
    dotnet run --project ../example

## Compile to a 64-bit Linux binary (Prepares the .NET application for deployment to Linux (specifically 64-bit) as a self-contained package. Self-Contained Deployment: Includes the .NET runtime and all dependencies within the published output, enabling the application to run on systems without requiring a separately installed .NET runtime. Optimizes the size of the published output by removing unused parts of the framework, reducing the application's footprint.)
    dotnet publish -c Release -r linux-x64 --self-contained true /p:PublishTrimmed=true

## To compile to a 64-bit Windows executable (Prepares the .NET application for deployment to Windows (specifically 64-bit) as a self-contained package. Self-Contained Deployment: Includes the .NET runtime and all dependencies within the published output, enabling the application to run on systems without requiring a separately installed .NET runtime. Optimizes the size of the published output by removing unused parts of the framework, reducing the application's footprint.)
    dotnet publish -c Release -r win-x64 --self-contained true /p:PublishTrimmed=true
