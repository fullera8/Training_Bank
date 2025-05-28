# Dockerfile for the MSTest project using /backendapp and /backendsrc

FROM mcr.microsoft.com/dotnet/sdk:8.0
WORKDIR /backendsrc
COPY ../ ./
RUN dotnet restore Training_Bank_Backend.Tests/Training_Bank_Backend.Tests.csproj
RUN dotnet build Training_Bank_Backend.Tests/Training_Bank_Backend.Tests.csproj --no-restore
CMD ["dotnet", "test", "Training_Bank_Backend.Tests/Training_Bank_Backend.Tests.csproj", "--no-build", "--logger:trx"]