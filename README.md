# RESTful API Practice

Hands-on ASP.NET Core Web API projects: CRUD endpoints, a layered API over SQL Server stored procedures, API clients (console and JavaScript), and image upload and download.

![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![.NET 8](https://img.shields.io/badge/.NET-8.0-512BD4?style=flat&logo=dotnet&logoColor=white)
![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-Web_API-512BD4?style=flat&logo=dotnet&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat&logo=swagger&logoColor=black)

## Projects

| Folder | What it covers |
|---|---|
| [`CRUD Operation by Restful API without database`](CRUD%20Operation%20by%20Restful%20API%20without%20database) | Students API on in-memory data: list all, passed and failed students, class average, get by id, add, update and delete. Includes a console client that calls every endpoint with `HttpClient`. |
| [`CRUD operation for students with restfullApi & more`](CRUD%20operation%20for%20students%20with%20restfullApi%20%26%20more) | Layered solution: Web API → business layer → ADO.NET data layer that calls SQL Server stored procedures. Adds teacher register and login, and an HTML / CSS / JavaScript client that consumes the API. |
| [`GetImageFromServer`](GetImageFromServer) | Upload an image and download it back by file name. |
| [`UploadImageToAFolder`](UploadImageToAFolder) | Upload an image to a folder on the server. |

## Students API (layered project)

| Method | Route | Description |
|---|---|---|
| GET | `api/Students/GetAllStudents` | All students |
| GET | `api/Students/GetPassedStudents` | Students who passed |
| GET | `api/Students/GetAverageGrade` | Average grade |
| GET | `api/Students/GetStudentsWithMaxGrade` | Top students |
| GET | `api/Students/GetStudentById/{id}` | One student |
| POST | `api/Students/AddStudents` | Add a student |
| PUT | `api/Students/UpdateStudent/{id}` | Update a student |
| PUT | `api/Students/DeleteStudent` | Delete a student |
| POST | `api/Teachers/Register` | Register a teacher |
| POST | `api/Teachers/Login` | Teacher login |

## Run locally

Requirements: .NET 8 SDK, and SQL Server for the layered project.

1. Open a project's `.sln` / `.slnx` in Visual Studio 2022, or run `dotnet run` inside the project folder.
2. Open `/swagger` in the browser to try the endpoints.
3. For the layered project, create a local `StudentsDB` database with the stored procedures used in `StudentDataAccsessLayer`. The data layer connects with Windows authentication (`Server=localhost;Database=StudentsDB;Trusted_Connection=True`).
