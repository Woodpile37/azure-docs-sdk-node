---
title: Azure WebPubSubManagement client library for JavaScript
keywords: Azure, javascript, SDK, API, @azure/arm-webpubsub, webpubsub
author: ramya-rao-a
ms.author: ramyar
ms.date: 08/31/2021
ms.topic: reference
ms.prod: azure
ms.technology: azure
ms.devlang: javascript
ms.service: webpubsub
---

# Azure WebPubSubManagement client library for JavaScript - Version 1.0.0-beta.1 


This package contains an isomorphic SDK (runs both in Node.js and in browsers) for Azure WebPubSubManagement client.

REST API for Azure WebPubSub Service

[Source code](https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-webpubsub_1.0.0-beta.1/sdk/web-pubsub/arm-webpubsub) |
[Package (NPM)](https://www.npmjs.com/package/@azure/arm-webpubsub) |
[API reference documentation](https://docs.microsoft.com/javascript/api/@azure/arm-webpubsub) |
[Samples](https://github.com/Azure-Samples/azure-samples-js-management)

## Getting started

### Currently supported environments

- [LTS versions of Node.js](https://nodejs.org/about/releases/)
- Latest versions of Safari, Chrome, Edge and Firefox.

### Prerequisites

- An [Azure subscription][azure_sub].

### Install the `@azure/arm-webpubsub` package

Install the Azure WebPubSubManagement client library for JavaScript with `npm`:

```bash
npm install @azure/arm-webpubsub
```

### Create and authenticate a `WebPubSubManagementClient`

To create a client object to access the Azure WebPubSubManagement API, you will need the `endpoint` of your Azure WebPubSubManagement resource and a `credential`. The Azure WebPubSubManagement client can use Azure Active Directory credentials to authenticate.
You can find the endpoint for your Azure WebPubSubManagement resource in the [Azure Portal][azure_portal].

#### Using an Azure Active Directory Credential

You can authenticate with Azure Active Directory using the [Azure Identity library][azure_identity]. To use the [DefaultAzureCredential][defaultazurecredential] provider shown below, or other credential providers provided with the Azure SDK, please install the `@azure/identity` package:

```bash
npm install @azure/identity
```

You will also need to register a new AAD application and grant access to Azure WebPubSubManagement by assigning the suitable role to your service principal (note: roles such as `"Owner"` will not grant the necessary permissions).
Set the values of the client ID, tenant ID, and client secret of the AAD application as environment variables: `AZURE_CLIENT_ID`, `AZURE_TENANT_ID`, `AZURE_CLIENT_SECRET`.

```javascript
const { WebPubSubManagementClient } = require("@azure/arm-webpubsub");
const { DefaultAzureCredential } = require("@azure/identity");
const client = new WebPubSubManagementClient("<endpoint>", new DefaultAzureCredential());
```

## Key concepts

### WebPubSubManagementClient

`WebPubSubManagementClient` is the primary interface for developers using the Azure WebPubSubManagement client library. Explore the methods on this client object to understand the different features of the Azure WebPubSubManagement service that you can access.

## Troubleshooting

### Logging

Enabling logging may help uncover useful information about failures. In order to see a log of HTTP requests and responses, set the `AZURE_LOG_LEVEL` environment variable to `info`. Alternatively, logging can be enabled at runtime by calling `setLogLevel` in the `@azure/logger`:

```javascript
import { setLogLevel } from "@azure/logger";
setLogLevel("info");
```

For more detailed instructions on how to enable logs, you can look at the [@azure/logger package docs](https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-webpubsub_1.0.0-beta.1/sdk/core/logger).

## Next steps

Please take a look at the [samples](https://github.com/Azure-Samples/azure-samples-js-management) directory for detailed examples on how to use this library.

## Contributing

If you'd like to contribute to this library, please read the [contributing guide](https://github.com/Azure/azure-sdk-for-js/blob/@azure/arm-webpubsub_1.0.0-beta.1/CONTRIBUTING.md) to learn more about how to build and test the code.

## Related projects

- [Microsoft Azure SDK for JavaScript](https://github.com/Azure/azure-sdk-for-js)

![Impressions](https://azure-sdk-impressions.azurewebsites.net/api/impressions/azure-sdk-for-js%2Fsdk%2Fweb-pubsub%2Farm-webpubsub%2FREADME.png)

[azure_cli]: https://docs.microsoft.com/cli/azure
[azure_sub]: https://azure.microsoft.com/free/
[azure_sub]: https://azure.microsoft.com/free/
[azure_portal]: https://portal.azure.com
[azure_identity]: https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-webpubsub_1.0.0-beta.1/sdk/identity/identity
[defaultazurecredential]: https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-webpubsub_1.0.0-beta.1/sdk/identity/identity#defaultazurecredential
