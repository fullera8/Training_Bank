FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /backendapp
EXPOSE 8080

FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /backendsrc

# Copy the .csproj file first and restore dependencies.
# This path is relative to the build context, which is /workspaces/Training_Bank/backend/Training_Bank_Backend/
# So, "Training_Bank_Backend.csproj" is correct.
COPY Training_Bank_Backend.csproj ./
RUN dotnet restore Training_Bank_Backend.csproj

# Copy the rest of your application's source code from the build context.
COPY . ./

# Publish the application, specifying the project file.
# The WORKDIR is still /backendsrc, where Training_Bank_Backend.csproj now resides.
RUN dotnet publish Training_Bank_Backend.csproj -c Release -o /backendapp/publish

FROM base AS final
WORKDIR /backendapp
COPY --from=build /backendapp/publish .
ENTRYPOINT ["dotnet", "Training_Bank_Backend.dll"]