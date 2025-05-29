FROM mcr.microsoft.com/dotnet/sdk:8.0
WORKDIR /backendsrc
COPY . ./
WORKDIR /backendsrc/Training_Bank_Backend.Tests
RUN dotnet restore
RUN dotnet build --no-restore
CMD ["dotnet", "test", "--no-build", "--logger:trx"]