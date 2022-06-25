---
title: Azure RedisEnterpriseManagement client library for JavaScript
keywords: Azure, javascript, SDK, API, @azure/arm-redisenterprisecache, cache
author: qiaozha
ms.author: qiaozha
ms.date: 06/25/2022
ms.topic: reference
ms.devlang: javascript
ms.service: cache
---
# Azure RedisEnterpriseManagement client library for JavaScript - Version 2.1.1-alpha.20220420.3 


This package contains an isomorphic SDK (runs both in Node.js and in browsers) for Azure RedisEnterpriseManagement client.

REST API for managing Redis Enterprise resources in Azure.

[Source code](https://github.com/Azure/azure-sdk-for-js/tree/main/sdk/redisenterprise/arm-redisenterprisecache) |
[Package (NPM)](https://www.npmjs.com/package/@azure/arm-redisenterprisecache) |
[API reference documentation](/javascript/api/@azure/arm-redisenterprisecache) |
[Samples](https://github.com/Azure-Samples/azure-samples-js-management)

## Getting started

### Currently supported environments

- [LTS versions of Node.js](https://nodejs.org/about/releases/)
- Latest versions of Safari, Chrome, Edge and Firefox.

See our [support policy](https://github.com/Azure/azure-sdk-for-js/blob/main/SUPPORT.md) for more details.

### Prerequisites

- An [Azure subscription][azure_sub].

### Install the `@azure/arm-redisenterprisecache` package

Install the Azure RedisEnterpriseManagement client library for JavaScript with `npm`:

```bash
npm install @azure/arm-redisenterprisecache
```

### Create and authenticate a `RedisEnterpriseManagementClient`

To create a client object to access the Azure RedisEnterpriseManagement API, you will need the `endpoint` of your Azure RedisEnterpriseManagement resource and a `credential`. The Azure RedisEnterpriseManagement client can use Azure Active Directory credentials to authenticate.
You can find the endpoint for your Azure RedisEnterpriseManagement resource in the [Azure Portal][azure_portal].

You can authenticate with Azure Active Directory using a credential from the [@azure/identity][azure_identity] library or [an existing AAD Token](https://github.com/Azure/azure-sdk-for-js/blob/master/sdk/identity/identity/samples/AzureIdentityExamples.md#authenticating-with-a-pre-fetched-access-token).

To use the [DefaultAzureCredential][defaultazurecredential] provider shown below, or other credential providers provided with the Azure SDK, please install the `@azure/identity` package:

```bash
npm install @azure/identity
```

You will also need to **register a new AAD application and grant access to Azure RedisEnterpriseManagement** by assigning the suitable role to your service principal (note: roles such as `"Owner"` will not grant the necessary permissions).
Set the values of the client ID, tenant ID, and client secret of the AAD application as environment variables: `AZURE_CLIENT_ID`, `AZURE_TENANT_ID`, `AZURE_CLIENT_SECRET`.

For more information about how to create an Azure AD Application check out [this guide](/azure/active-directory/develop/howto-create-service-principal-portal).

```javascript
const { RedisEnterpriseManagementClient } = require("@azure/arm-redisenterprisecache");
const { DefaultAzureCredential } = require("@azure/identity");
// For client-side applications running in the browser, use InteractiveBrowserCredential instead of DefaultAzureCredential. See https://aka.ms/azsdk/js/identity/examples for more details.

const subscriptionId = "00000000-0000-0000-0000-000000000000";
const client = new RedisEnterpriseManagementClient(new DefaultAzureCredential(), subscriptionId);

// For client-side applications running in the browser, use this code instead:
// const credential = new InteractiveBrowserCredential({
//   tenantId: "<YOUR_TENANT_ID>",
//   clientId: "<YOUR_CLIENT_ID>"
// });
// const client = new RedisEnterpriseManagementClient(credential, subscriptionId);
```


### JavaScript Bundle
To use this client library in the browser, first you need to use a bundler. For details on how to do this, please refer to our [bundling documentation](https://aka.ms/AzureSDKBundling).

## Key concepts

### RedisEnterpriseManagementClient

`RedisEnterpriseManagementClient` is the primary interface for developers using the Azure RedisEnterpriseManagement client library. Explore the methods on this client object to understand the different features of the Azure RedisEnterpriseManagement service that you can access.

## Troubleshooting

### Logging

Enabling logging may help uncover useful information about failures. In order to see a log of HTTP requests and responses, set the `AZURE_LOG_LEVEL` environment variable to `info`. Alternatively, logging can be enabled at runtime by calling `setLogLevel` in the `@azure/logger`:

```javascript
const { setLogLevel } = require("@azure/logger");
setLogLevel("info");
```

For more detailed instructions on how to enable logs, you can look at the [@azure/logger package docs](https://github.com/Azure/azure-sdk-for-js/tree/main/sdk/core/logger).

## Next steps

Please take a look at the [samples](https://github.com/Azure-Samples/azure-samples-js-management) directory for detailed examples on how to use this library.

## Contributing

If you'd like to contribute to this library, please read the [contributing guide](https://github.com/Azure/azure-sdk-for-js/blob/main/CONTRIBUTING.md) to learn more about how to build and test the code.

## Related projects

- [Microsoft Azure SDK for JavaScript](https://github.com/Azure/azure-sdk-for-js)

![Impressions](https://azure-sdk-impressions.azurewebsites.net/api/impressions/azure-sdk-for-js%2Fsdk%2Fredisenterprise%2Farm-redisenterprisecache%2FREADME.png)

[azure_cli]: /cli/azure
[azure_sub]: https://azure.microsoft.com/free/
[azure_sub]: https://azure.microsoft.com/free/
[azure_portal]: https://portal.azure.com
[azure_identity]: https://github.com/Azure/azure-sdk-for-js/tree/main/sdk/identity/identity
[defaultazurecredential]: https://github.com/Azure/azure-sdk-for-js/tree/main/sdk/identity/identity#defaultazurecredential
