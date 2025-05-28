# Dockerfile for the .NET 8 MVC backend using /backendapp and /backendsrc

FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /backendapp
EXPOSE 8080

FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /backendsrc
COPY ../ ./
RUN dotnet restore Training_Bank_Backend/Training_Bank_Backend.csproj
RUN dotnet publish Training_Bank_Backend/Training_Bank_Backend.csproj -c Release -o /backendapp/publish

FROM base AS final
WORKDIR /backendapp
COPY --from=build /backendapp/publish .
ENTRYPOINT ["dotnet", "Training_Bank_Backend.dll"]