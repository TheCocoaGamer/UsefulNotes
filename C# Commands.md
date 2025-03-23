## ⚙️ **C# / .NET CLI Commands Cheat Sheet**

#### **1. Build a Solution and Log Output**
```sh
dotnet build TerrariaHardcore.sln > logs.log 2>&1
```
> Compile and log everything to a file. Works when a `.sln` is in the root.

---

#### **2. Run a Project**
```sh
dotnet run --project path/to/YourProject.csproj
```
> Runs the specified project. You can also run from within the project folder directly.

---

#### **3. Create a New Console App**
```sh
dotnet new console -n YourAppName
```
> Initializes a new console project in a folder called `YourAppName`.

---

#### **4. Restore NuGet Packages**
```sh
dotnet restore
```
> Pulls down all NuGet dependencies based on the `.csproj` or `.sln`.

---

#### **5. Add a NuGet Package**
```sh
dotnet add package Newtonsoft.Json
```
> Adds `Newtonsoft.Json` (or any package) to your project.

---

#### **6. Publish a Release Build**
```sh
dotnet publish -c Release -o ./publish
```
> Builds your app in Release mode and dumps the result into `./publish`.

---

#### **7. List Installed SDKs and Runtimes**
```sh
dotnet --list-sdks
dotnet --list-runtimes
```
> Shows what SDKs and runtimes are installed. Helps when debugging version issues.

---

#### **8. Check Project Version**
```sh
dotnet --version
```
> Returns the active SDK version. Useful when things start randomly breaking.

---

#### **9. Create a Class Library**
```sh
dotnet new classlib -n MyLibrary
```
> Starts a reusable library project you can import elsewhere.

---
