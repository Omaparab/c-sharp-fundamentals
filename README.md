# C# Learning and Dataverse Projects

This repository contains C# practice exercises and a console application for managing employee records in Microsoft Dataverse.

## Projects

### Practice

`Practice` is a .NET console project with introductory examples organized by topic:

- **Day 1:** variables and data types, conditionals, and loops
- **Day 2:** classes, constructors, encapsulation, and methods
- **Day 3:** collections, exception handling, file operations, and triangle patterns
- **Additional:** abstract classes and interfaces

The current program entry point runs the triangle-pattern example. Other exercise calls in `Program.cs` are commented out; enable the relevant call to run a different example.

Run from the repository root:

```powershell
dotnet run --project .\Practice\HelloWorld.csproj
```

### AttendanceSystem

`AttendanceSystem` is a menu-driven console app that connects to Microsoft Dataverse and provides employee record operations:

- Add an employee
- List employees
- Update an employee
- Delete an employee

Employee records use the `oma_employee` table, with a department lookup to `oma_department`. The app expects the custom columns used in `Employee_Service.cs`, including employee code, name, email, experience years, and department name.

Before running the app:

1. Install the .NET 10 SDK.
2. Configure and verify the Dataverse organization URL and OAuth app registration in `AttendanceSystem/services/DataverseService.cs`.
3. Ensure the signed-in identity has permission to access the Dataverse environment and the required custom tables and columns exist.

Run from the repository root:

```powershell
dotnet run --project .\AttendanceSystem\AttendanceSystem.csproj
```

The app prints the connection status before displaying its menu. Choose **5** to exit.

## Requirements

- .NET 10 SDK
- For `AttendanceSystem`, access to a Dataverse environment configured for the app's OAuth connection

## Repository Layout

```text
C-Sharp/
├── AttendanceSystem/
│   ├── model/
│   │   └── Employee.cs
│   ├── services/
│   │   ├── DataverseService.cs
│   │   └── Employee_Service.cs
│   ├── AttendanceSystem.csproj
│   └── Program.cs
├── Practice/
│   ├── additional/
│   ├── day1/
│   ├── day2/
│   ├── day3/
│   ├── HelloWorld.csproj
│   └── Program.cs
└── README.md
```

## Build

Build either project from the repository root:

```powershell
dotnet build .\Practice\HelloWorld.csproj
dotnet build .\AttendanceSystem\AttendanceSystem.csproj
```
