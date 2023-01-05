FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
COPY . /app
WORKDIR /app
EXPOSE 5000/tcp
ENTRYPOINT ["dotnet", "AuthWebApi.dll"]