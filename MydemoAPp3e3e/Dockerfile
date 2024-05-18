# Use the official .NET SDK image as a base image
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env

# Set the working directory inside the container
WORKDIR /app

# Copy the necessary files to the container
COPY . ./

# Publish the application
RUN dotnet publish -c Release -o out

# Create a runtime image
FROM mcr.microsoft.com/dotnet/aspnet:6.0

# Set the working directory to /app
WORKDIR /app

# Copy the published output from the build environment
COPY --from=build-env /app/out .

# Expose port 80 for the web application
EXPOSE 80

# Specify the entry point for the application
ENTRYPOINT ["dotnet", "MydemoAPp3e3e.dll"]
