# TikToken API
---
### Docker Stuff
---
Generate selfsigned certificate on Windows:
```powershell
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\tiktoken.pfx -p THE_PASSWORD
dotnet dev-certs https --trust
```

Run container with lots of parameters:
```powershell
docker run --rm -it -p 8001:443 -e ASPNETCORE_URLS="https://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_Kestrel__Certificates__Default__Password="THE_PASSWORD" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/tiktoken.pfx -v $env:USERPROFILE\.aspnet\https:/https/ tiktoken
```
