# Build avec .NET Core
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build

WORKDIR /app

COPY  *.csproj .

RUN dotnet restore

COPY . .

RUN dotnet publish -c Release -o /out Worker.csproj

# Execution
FROM mcr.microsoft.com/dotnet/core/runtime:3.1

WORKDIR /app

COPY --from=build /app/out .

CMD ["dotnet", "worker.dll"]