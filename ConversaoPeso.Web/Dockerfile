FROM mcr.microsoft.com/dotnet/sdk:5.0
WORKDIR /app

COPY *.csproj ./
RUN dotnet restore

COPY . ./
RUN dotnet publish -c release -o /app --no-restore

FROM mcr.microsoft.com/dotnet/aspnet:5.0
WORKDIR /app
COPY --from=0 /app ./
ENTRYPOINT ["dotnet", "ConversaoPeso.Web.dll"]
