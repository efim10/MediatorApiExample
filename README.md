# MediatorApiExample

ASP.NET Core Web API example using MediatR, MongoDB, FluentValidation and NSwag (OpenAPI). This project demonstrates a simple mediator-based architecture with commands, handlers, services and validation.

## Requirements
- .NET 10 SDK installed: https://dotnet.microsoft.com
- MongoDB instance reachable from the app (local or remote)

## Configuration
The project reads MongoDB settings from configuration section `MediatorApiDatabaseSettings`. Provide these keys in `appsettings.json` or environment variables.

Example `appsettings.json` snippet:

```json
{
  "MediatorApiDatabaseSettings": {
    "ConnectionString": "mongodb://localhost:27017",
    "DatabaseName": "MediatorApiExampleDb"
  }
}
```

## How to build and run
From the repository root:

1. Restore packages
   - `dotnet restore MediatorApiExample/MediatorApiExample.csproj`

2. Build
   - `dotnet build MediatorApiExample/MediatorApiExample.csproj`

3. Run
   - `dotnet run --project MediatorApiExample/MediatorApiExample.csproj`

The app listens on the configured urls (by default `https://localhost:5001`).

## API endpoints
Controllers use attribute routing under `/api/{controller}`. Two controllers are available:

- Customer endpoints (examples)
  - GET list: `GET /api/customer/GetCustomers`
  - GET single: `GET /api/customer/GetCustomer?id={id}`
  - POST create: `POST /api/customer` (body: create command)
  - PUT update: `PUT /api/customer` (body: update command)
  - DELETE delete: `DELETE /api/customer` (body: delete command)

- Order endpoints (examples)
  - GET list: `GET /api/order/GetOrders`
  - GET single: `GET /api/order/GetOrder?id={id}`
  - POST create: `POST /api/order`
  - PUT update: `PUT /api/order`
  - DELETE delete: `DELETE /api/order`

Notes:
- Swagger UI (`https://localhost:5001/swagger`).