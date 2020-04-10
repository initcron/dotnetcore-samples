FROM mcr.microsoft.com/dotnet/core/sdk:3.1

WORKDIR /source 

COPY . . 

RUN dotnet restore 

WORKDIR /source/aspnetapp

RUN dotnet publish -c release -o /app 

EXPOSE 80 

WORKDIR /app

ENV ASPNETCORE_URLS http://*:80

CMD dotnet aspnetapp.dll

