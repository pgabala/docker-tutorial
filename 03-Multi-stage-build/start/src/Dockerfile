FROM microsoft/dotnet:2.1-sdk-alpine AS build
WORKDIR /src
COPY MultiStage.csproj .
RUN dotnet restore MultiStage.csproj
COPY . .
RUN dotnet build MultiStage.csproj -c Release
RUN dotnet publish MultiStage.csproj -c Release -o /app

FROM microsoft/dotnet:2.1-aspnetcore-runtime-alpine
WORKDIR /app
COPY --from=build /app .
ENV ASPNETCORE_URLS http://+:5000
EXPOSE 5000
CMD ["dotnet", "MultiStage.dll"]