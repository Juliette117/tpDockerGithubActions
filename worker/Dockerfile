# Build avec .NET Core
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build

WORKDIR /worker

COPY  *.csproj .

RUN dotnet restore

COPY . .

RUN dotnet publish -c Release -o /out Worker.csproj

# Execution
FROM mcr.microsoft.com/dotnet/core/runtime:3.1

WORKDIR /worker

COPY --from=build /app/out .

EXPOSE 80

CMD ["dotnet", "worker.dll"]