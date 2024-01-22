# .NET 8.0 Container Images

The .NET 8.0 container images now include a non-root user by default.

> ### Non-Root User Included By Default
> The .NET Linux container images include a new non-root user named `app` with the UID 1654.  
> The UID is provided in an environment variable, `$APP_UID`.  
> You can opt into this new user by adding the line `USER $APP_UID` to your Dockerfile.

> [!IMPORTANT]
> The name of this user may conflict with an existing user defined by your application's Dockerfile.

See https://github.com/dotnet/dotnet-docker/discussions/4995.
