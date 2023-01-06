#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["webapi.aowproducts/webapi.aowproducts.csproj", "webapi.aowproducts/"]
RUN dotnet restore "webapi.aowproducts/webapi.aowproducts.csproj"
COPY . .
WORKDIR "/src/webapi.aowproducts"
RUN dotnet build "webapi.aowproducts.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "webapi.aowproducts.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "webapi.aowproducts.dll"]
