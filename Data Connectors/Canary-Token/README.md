# Canary Toekn - Polling Data Connector

```
DO NOT USE THIS DATA CONNECTOR IN PRODUCTION, since it relies on a query parameter (newer_than) in the API endpoint that is soon to be deprecated.
```

This repository contains an ARM (Azure Resource Manager) template for deploying a Codeless Connector for Microsoft Sentinel. This connector allows you to ingest alerts and incidents from **Canary Token** into Microsoft Sentinel.

## Features
- Ingest alerts from Canary Portal
- Simplified deployment using an ARM template
- Supports filtering and transformation of alerts through a Data Collection Rule
- DOES NOT require exposing a HTTP endpoint to the internet

## Prerequisites
Before you can deploy this solution, ensure that you have the following:

1. **Azure Subscription**: You need an active Azure subscription.
2. **Microsoft Sentinel**: Ensure Microsoft Sentinel is set up in your subscription/resource group.
3. **Permissions**: You need sufficient permissions in the Azure subscription to deploy the ARM template and manage resources.
4. **Canary Token Portal**: You need access to the Canary Token portal from which you want to ingest alerts.


## Deployment Steps

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


## Verify Deployment
Once the deployment is complete, verify that the Codeless Connector has been successfully created in your Microsoft Sentinel instance. You should be able to see the connector listed under **Data Connectors** in Microsoft Sentinel.

## Configuration
Once the connector is deployed, you'll need to configure it to connect to your Canary Portal. This typically involves providing API token for log ingestion. Check the data connector page for more instructions.

## Known Limitations
- The data connector can run only every 1 minute (minimum)
- The data connector uses a query parameter 'newer_than' which is said to be DEPRECATED soon, making the data connector fail

## Troubleshooting
- If you encounter any issues during deployment or configuration, refer to the Azure Activity Log for detailed error messages.
- Ensure that the Organization ID is accurate.
- Ensure that the API Token is accurate, and has necessary permissions.

## Contributing
Feel free to open issues and pull requests if you encounter any bugs or want to suggest improvements. Contributions are welcome!