FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS BUILD
WORKDIR /source 
COPY . . 
RUN dotnet restore 
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app 

FROM mcr.microsoft.com/dotnet/core/runtime:3.1 AS RUN 
WORKDIR /app
COPY --from=build /app .
EXPOSE 80 
CMD dotnet aspnetapp.dll


