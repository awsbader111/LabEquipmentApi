# LabEquipmentApi

ASP.NET Core Web API (.NET 10) for managing laboratory equipment, using PostgreSQL with EF Core Code First.

## Run

1. PostgreSQL on `localhost:5432` (user `postgres`, password `pass`).
2. From the project folder:
   ```
   dotnet ef database update
   dotnet run --launch-profile https
   ```
3. Open `https://localhost:7196/swagger`.

## Endpoints

| Method | Route | Description |
|---|---|---|
| GET | `/api/equipment` | All equipment |
| GET | `/api/equipment/{id}` | One item (404 if missing) |
| GET | `/api/equipment/available` | Available equipment, sorted by name (DTO, Mapster projection) |
| GET | `/api/equipment/room-summary` | Total and available count per room |
| POST | `/api/equipment` | Create equipment from `CreateEquipmentRequest` (FluentValidation) |
| PUT | `/api/equipment/{id}` | Update equipment (scaffolded) |
| DELETE | `/api/equipment/{id}` | Delete equipment (scaffolded) |
