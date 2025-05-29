FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /backendapp
EXPOSE 8080

FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /backendsrc
COPY . ./
WORKDIR /backendsrc/Training_Bank_Backend
RUN dotnet restore
RUN dotnet publish -c Release -o /backendapp/publish

FROM base AS final
WORKDIR /backendapp
COPY --from=build /backendapp/publish .
ENTRYPOINT ["dotnet", "Training_Bank_Backend.dll"]