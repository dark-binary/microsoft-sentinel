# Defender XDR - Cross-tenant Data Connector

This repository contains an ARM (Azure Resource Manager) template for deploying a Codeless Connector for Microsoft Sentinel. This connector allows you to ingest alerts and incidents from **Defender XDR** from a different tenant into Microsoft Sentinel. Unlike the native Defender XDR data connector, which only supports data ingestion from the same tenant, this solution supports cross-tenant data ingestion.

## Features
- Ingest alerts and incidents from Defender XDR from a different tenants
- Simplified deployment using an ARM template
- Supports filtering and transformation of both alerts and incidents through a Data Collection Rule

## Prerequisites
Before you can deploy this solution, ensure that you have the following:

1. **Azure Subscription**: You need an active Azure subscription.
2. **Microsoft Sentinel**: Ensure Microsoft Sentinel is set up in your subscription/resource group.
3. **Permissions**: You need sufficient permissions in the Azure subscription to deploy the ARM template and manage resources.
4. **Defender XDR Tenant**: You need access to the Defender XDR instance from which you want to ingest alerts and incidents.
5. **Entra ID App Registration**: Ensure that you have registered an Entra ID app registration that has permissions to read Defender XDR data from the other tenant. 'SecurityAlert.Read.All' and 'SecurityIncident.Read.All' graph permissions are the required permissions.


## Deployment Steps

### Option 1: Deploy using Template Specs

1. Go to the [Azure Portal](https://portal.azure.com/)
2. In the top search bar, search for **"Template Specs"**
3. Click **"Template Specs"**
4. Click **"Create template spec"**
5. Provide appropriate inputs for name, subscription and resource group in which the template spec is to be stored.
6. Copy and paste the contents of `maintemplate.json` into the **Edit Template** section.
7. Click **"Review + Create"** and then **"Create"** to deploy.
8. Open the newly create Template spec
9. Click the **"Deploy"** button, and provide the appropriate inputs
10. Click **"Review + Create"** and then **"Create"** to deploy.


### Option 2: Easy Deploy
Click the button below to quickly deploy this solution to your Azure subscription.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri=https://raw.githubusercontent.com/dark-binary/microsoft-sentinel/main/Data%20Connectors/Defender%20XDR%20-%20Cross-tenant/maintemplate.json)


## Verify Deployment
Once the deployment is complete, verify that the Codeless Connector has been successfully created in your Microsoft Sentinel instance. You should be able to see the connector listed under **Data Connectors** in Microsoft Sentinel.

## Configuration
Once the connector is deployed, you'll need to configure it to connect to your Defender XDR instance from a different tenant. This typically involves providing service principal (app registration) credentials for cross-tenant data ingestion. Check the data connector page for more instructions.

## Troubleshooting
- If you encounter any issues during deployment or configuration, refer to the Azure Activity Log for detailed error messages.
- Ensure that the necessary permissions and admin consent have been granted for the app registration.
- Ensure that the Tenant ID, Client ID and Client Secret are accurate.

## Contributing
Feel free to open issues and pull requests if you encounter any bugs or want to suggest improvements. Contributions are welcome!