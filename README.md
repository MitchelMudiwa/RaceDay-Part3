# RaceDay

RaceDay is a race event system. Organisers create events and categories, and participants browse and enrol. The project is split into three parts:

1. **Part 1:** planning (ERD, API endpoint plan, SQL script)
2. **Part 2:** RESTful API in C# (ASP.NET Core) with unit tests
3. **Part 3:** MVC web app that consumes the API, plus Azure Blob Storage and Docker

## Projects in this repo

| Folder | What it is |
| `PART 2 c#` | The RESTful API |
| `RaceDay.Mvc` | The MVC web app (Part 3) |
| `RaceDay.Tests` | Unit tests |

## Features built so far

- Register, log in and log out (roles: Organizer and Participant)
- Role-based menu and page locks
- Events: list, details, create, edit, delete (Organizer only for changes)
- Categories: list, add, edit, delete (Organizer only)
- <Add enrolments, results and banner images here when they are done>

The MVC app never touches the database. It only talks to the API, and it keeps the API login session inside its own session.

## Run it locally

You need the .NET 10 SDK.

1. Start the **API** first:

```
cd "PART 2 c#"
dotnet run --launch-profile https
```

It listens on `https://localhost:7195`.

2. Then start the **MVC app** in a second terminal:

```
cd RaceDay.Mvc
dotnet run --launch-profile https
```

It listens on `https://localhost:7184`.

The MVC app reads the API address from `ApiSettings:BaseUrl` in `RaceDay.Mvc/appsettings.json`.

Database setup: <add the steps from your Part 2 here>

## Run with Docker

<Add the Docker build and run commands here once the Dockerfile is finished>

## CI/CD

A GitHub Actions workflow (`.github/workflows/ci.yml`) builds the projects and runs the unit tests on every push.


