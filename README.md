# Azure Function Debug Sample

This Azure Function App is just used for debuging after infrastructure deployment in a public or private networking.

## Build and publish the function app.

```bash
dotnet build -c Release
```

```bash
dotnet publish -c Release
```

## Deployment

### With Azure Function Core Tools
```bash
func azure functionapp publish <functionapp_name>
```

### With Azure CLI
```bash
cd bin/Release/net8.0/publish

# Create a zip file of the publish output
zip -r ../../../../function.zip .

az functionapp deployment source config-zip --name <functionapp_name> --resource-group <resource_group_name> --src <path_to_zip_file>
```