#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
EXPOSE 80
EXPOSE 443
FROM base AS final
WORKDIR /app
ENTRYPOINT ["dotnet", "webapi.aowproducts.dll"]
