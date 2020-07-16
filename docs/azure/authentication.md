---
title: Общие сведения о проверке подлинности в библиотеках Azure для .NET
description: Описание различных способов проверки подлинности с помощью пакета Azure SDK для .NET.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 5ed29d5485dc7f59bcc757c8903116edf6bd5d7d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174873"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a><span data-ttu-id="c81b3-103">Проверка подлинности с помощью пакета Azure SDK для .NET</span><span class="sxs-lookup"><span data-stu-id="c81b3-103">Authenticate with the Azure SDK for .NET</span></span>

## <a name="recommended-azureidentity"></a><span data-ttu-id="c81b3-104">Рекомендация: Azure.Identity</span><span class="sxs-lookup"><span data-stu-id="c81b3-104">Recommended: Azure.Identity</span></span>

<span data-ttu-id="c81b3-105">Новейшие пакеты в пакете Azure SDK для .NET используют для проверки подлинности общий пакет `Azure.Identity`.</span><span class="sxs-lookup"><span data-stu-id="c81b3-105">The latest packages in the Azure SDK for .NET use a common authentication package to authenticate, `Azure.Identity`.</span></span> <span data-ttu-id="c81b3-106">Именно этот пакет `Azure.Identity` является рекомендуемым по сравнению с другими механизмами проверки подлинности, описанными далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="c81b3-106">Using `Azure.Identity` is recommended over other authentication mechanisms described later in this document.</span></span> <span data-ttu-id="c81b3-107">Идентификаторы пакетов, поддерживающие учетные данные, предоставленные `Azure.Identity`, начинаются с *Azure.*</span><span class="sxs-lookup"><span data-stu-id="c81b3-107">Packages supporting the credentials provided by `Azure.Identity` have package identifiers starting with *Azure.*</span></span> <span data-ttu-id="c81b3-108">[Дополнительные сведения см. на странице последних выпусков в пакете Azure SDK для .NET](https://azure.github.io/azure-sdk/releases/latest/index.html#net).</span><span class="sxs-lookup"><span data-stu-id="c81b3-108">[For more information, see the latest releases in the Azure SDK for .NET](https://azure.github.io/azure-sdk/releases/latest/index.html#net).</span></span>

<span data-ttu-id="c81b3-109">Полные инструкции по использованию `Azure.Identity` в проекте см. в документации по [клиенту Azure Identity для .NET](/dotnet/api/overview/azure/identity-readme).</span><span class="sxs-lookup"><span data-stu-id="c81b3-109">For complete instructions on using `Azure.Identity` in your project, see the documentation for [Azure Identity client for .NET](/dotnet/api/overview/azure/identity-readme).</span></span>

> [!TIP]
> <span data-ttu-id="c81b3-110">Примеры использования Azure Identity для управления ресурсами Azure и доступа к ним см. в статье с [примерами пакетов для Azure Identity, управления ресурсами и хранилища](/samples/dotnet/samples/azure-identity-resource-management-storage/).</span><span class="sxs-lookup"><span data-stu-id="c81b3-110">See the [Azure Identity, Resource Management, and Storage sample](/samples/dotnet/samples/azure-identity-resource-management-storage/) for examples of using Azure Identity to manage and access Azure resources.</span></span>

<span data-ttu-id="c81b3-111">Сведения о проверке подлинности с помощью библиотек, которые не поддерживают Azure.Identity, см. в оставшейся части этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c81b3-111">To authenticate with libraries that don't support Azure.Identity, see the rest of this topic.</span></span>

## <a name="access-azure-resources"></a><span data-ttu-id="c81b3-112">Оценка ресурсов Azure</span><span class="sxs-lookup"><span data-stu-id="c81b3-112">Access Azure resources</span></span>

<span data-ttu-id="c81b3-113">Для взаимодействия с ресурсами Azure, например при получении секрета из Key Vault или сохранении BLOB-объекта в хранилище, многим библиотекам служб Azure требуется строка подключения или ключи для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c81b3-113">To interact with Azure resources, such as retrieving a secret from Key Vault or storing a blob in Storage, many Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="c81b3-114">Например, База данных SQL использует [стандартную строку подключения SQL](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="c81b3-114">For example, SQL Database uses a [standard SQL connection string](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core).</span></span> <span data-ttu-id="c81b3-115">Строки подключения службы используются в других службах Azure, таких как [Cosmos DB](/azure/cosmos-db/), [Кэш Azure для Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache) и [Служебная шина Azure](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span><span class="sxs-lookup"><span data-stu-id="c81b3-115">Service connection strings are used in other Azure services like [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="c81b3-116">Эти строки можно получить, воспользовавшись порталом Azure, CLI или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c81b3-116">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="c81b3-117">Также с помощью библиотек управления Azure для .NET можно выполнять запросы к ресурсам для создания строк подключения в коде.</span><span class="sxs-lookup"><span data-stu-id="c81b3-117">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="c81b3-118">Методы использования строки подключения зависят от продукта.</span><span class="sxs-lookup"><span data-stu-id="c81b3-118">The methods for using a connection string vary by product.</span></span> <span data-ttu-id="c81b3-119">[См. документацию по продукту Azure](/azure/?product=featured).</span><span class="sxs-lookup"><span data-stu-id="c81b3-119">[Refer to the documentation for your Azure product](/azure/?product=featured).</span></span>

## <a name="manage-azure-resources"></a><span data-ttu-id="c81b3-120">Управление ресурсами Azure</span><span class="sxs-lookup"><span data-stu-id="c81b3-120">Manage Azure resources</span></span>

[!include[Create service principal](includes/create-sp.md)]

<span data-ttu-id="c81b3-121">После создания субъекта-службы выполнить аутентификацию субъекта-службы для создания и администрирования ресурсов можно двумя способами.</span><span class="sxs-lookup"><span data-stu-id="c81b3-121">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="c81b3-122">Для обоих вариантов необходимо добавить следующие пакеты NuGet в проект.</span><span class="sxs-lookup"><span data-stu-id="c81b3-122">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="c81b3-123">Аутентификация с использованием учетных данных токена</span><span class="sxs-lookup"><span data-stu-id="c81b3-123">Authenticate with token credentials</span></span>

<span data-ttu-id="c81b3-124">Первый способ — создание объекта учетных данных токена в коде.</span><span class="sxs-lookup"><span data-stu-id="c81b3-124">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="c81b3-125">Учетные данные следует безопасно хранить в файле конфигурации, реестре или Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c81b3-125">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="c81b3-126">При создании субъекта-службы используйте значения *clientId*, *clientSecret* и *tenantId* из выходных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="c81b3-126">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="c81b3-127">Затем создайте точку входа объекта `Azure`, чтобы приступить к работе с API:</span><span class="sxs-lookup"><span data-stu-id="c81b3-127">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="c81b3-128">Аутентификация на основе файла</span><span class="sxs-lookup"><span data-stu-id="c81b3-128">File-based authentication</span></span>

<span data-ttu-id="c81b3-129">Аутентификация на основе файла позволяет поместить учетные данные субъекта-службы в текстовый файл и защитить его в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="c81b3-129">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](includes/file-based-auth.md)]

<span data-ttu-id="c81b3-130">Прочтите содержимое файла и создайте точку входа объекта `Azure`, чтобы приступить к работе с API:</span><span class="sxs-lookup"><span data-stu-id="c81b3-130">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
