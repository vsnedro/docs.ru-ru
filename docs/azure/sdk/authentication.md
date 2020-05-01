---
title: Аутентификация с использованием библиотек Azure для .NET
description: Аутентификация в библиотеках Azure для .NET
ms.date: 08/22/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: f6af813cd1423be8784b769b272756b2c8258392
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607873"
---
# <a name="authenticate-with-the-azure-libraries-for-net"></a><span data-ttu-id="21bb4-103">Аутентификация с использованием библиотек Azure для .NET</span><span class="sxs-lookup"><span data-stu-id="21bb4-103">Authenticate with the Azure Libraries for .NET</span></span>

## <a name="connect-to-services-with-connection-strings"></a><span data-ttu-id="21bb4-104">Подключение к службам с помощью строк подключения</span><span class="sxs-lookup"><span data-stu-id="21bb4-104">Connect to services with connection strings</span></span>

<span data-ttu-id="21bb4-105">Большинство библиотек службы Azure требуют строку подключения или ключ для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="21bb4-105">Most Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="21bb4-106">Например, база данных SQL использует стандартную строку подключения SQL:</span><span class="sxs-lookup"><span data-stu-id="21bb4-106">For example, SQL Database uses a standard SQL connection string:</span></span>

```csharp
var builder = new SqlConnectionStringBuilder();
builder.DataSource = "example.database.windows.net";
builder.InitialCatalog = "MyDatabase";
builder.UserID = "sampleuser@example"; // Format user ID as "user@server"
builder.Password = password;
builder.Encrypt = true;
builder.TrustServerCertificate = true;

using (var conn = new SqlConnection(builder.ConnectionString))
{
    conn.Open();
    // Do things with the connection...
    // ...
}
```

<span data-ttu-id="21bb4-107">Служба хранилища Azure использует ключ к хранилищу данных:</span><span class="sxs-lookup"><span data-stu-id="21bb4-107">Azure Storage uses a storage key:</span></span>

```csharp
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storageName
        + ";AccountKey=" + storageKey
        + ";EndpointSuffix=core.windows.net";

var account = CloudStorageAccount.Parse(storageConnectionString);
// Do things with the account here...
```

<span data-ttu-id="21bb4-108">Строки подключения службы используются в других службах Azure, таких как [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/), [Кэш Azure для Redis](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache) и [Служебная шина Azure](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span><span class="sxs-lookup"><span data-stu-id="21bb4-108">Service connection strings are used in other Azure services like [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/), [Azure Cache for Redis](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="21bb4-109">Эти строки можно получить, воспользовавшись порталом Azure, CLI или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21bb4-109">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="21bb4-110">Также с помощью библиотек управления Azure для .NET можно выполнять запросы к ресурсам для создания строк подключения в коде.</span><span class="sxs-lookup"><span data-stu-id="21bb4-110">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="21bb4-111">В этом фрагменте кода используются библиотеки управления для создания строки подключения учетной записи хранения:</span><span class="sxs-lookup"><span data-stu-id="21bb4-111">This snippet uses the management libraries to create a storage account connection string:</span></span>

```csharp
// Get a storage account
var storage = azure.StorageAccounts.GetByResourceGroup("myResourceGroup", "myStorageAccount");

// Extract the keys
var storageKeys = storage.GetKeys();

// Build the connection string
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storage.Name
        + ";AccountKey=" + storageKeys[0].Value
        + ";EndpointSuffix=core.windows.net";

// Connect
var account = CloudStorageAccount.Parse(storageConnectionString);

// Do things with the account here...
```

<span data-ttu-id="21bb4-112">Для других библиотек требуется, чтобы приложение работало с [субъектом-службой](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects), который разрешает приложению работать с предоставленными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="21bb4-112">Other libraries require your application to run with a [service principal](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) authorizing the application to run with granted credentials.</span></span> <span data-ttu-id="21bb4-113">Эта конфигурация похожа на действия проверки подлинности на основе объектов для библиотеки управления, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="21bb4-113">This configuration is similar to the object-based authentication steps for the management library listed below.</span></span>

## <a name="azure-management-libraries-for-net-authentication"></a><a name="mgmt-auth"></a><span data-ttu-id="21bb4-114">Библиотеки управления Azure для аутентификации .NET</span><span class="sxs-lookup"><span data-stu-id="21bb4-114">Azure management libraries for .NET authentication</span></span>

[!include[Create service principal](../includes/create-sp.md)]

<span data-ttu-id="21bb4-115">После создания субъекта-службы выполнить аутентификацию субъекта-службы для создания и администрирования ресурсов можно двумя способами.</span><span class="sxs-lookup"><span data-stu-id="21bb4-115">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="21bb4-116">Для обоих вариантов необходимо добавить следующие пакеты NuGet в проект.</span><span class="sxs-lookup"><span data-stu-id="21bb4-116">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="21bb4-117">Аутентификация с использованием учетных данных токена</span><span class="sxs-lookup"><span data-stu-id="21bb4-117">Authenticate with token credentials</span></span>

<span data-ttu-id="21bb4-118">Первый способ — создание объекта учетных данных токена в коде.</span><span class="sxs-lookup"><span data-stu-id="21bb4-118">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="21bb4-119">Учетные данные следует безопасно хранить в файле конфигурации, реестре или Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="21bb4-119">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
    clientSecret,
    tenantId,
    AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="21bb4-120">При создании субъекта-службы используйте значения *clientId*, *clientSecret* и *tenantId* из выходных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="21bb4-120">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="21bb4-121">Затем создайте точку входа объекта `Azure`, чтобы приступить к работе с API:</span><span class="sxs-lookup"><span data-stu-id="21bb4-121">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="21bb4-122">Аутентификация на основе файла</span><span class="sxs-lookup"><span data-stu-id="21bb4-122">File-based authentication</span></span>

<span data-ttu-id="21bb4-123">Аутентификация на основе файла позволяет поместить учетные данные субъекта-службы в текстовый файл и защитить его в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="21bb4-123">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](../includes/file-based-auth.md)]

<span data-ttu-id="21bb4-124">Прочтите содержимое файла и создайте точку входа объекта `Azure`, чтобы приступить к работе с API:</span><span class="sxs-lookup"><span data-stu-id="21bb4-124">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
