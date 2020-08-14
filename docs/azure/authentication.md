---
title: Общие сведения о проверке подлинности в библиотеках Azure для .NET
description: Описание различных способов проверки подлинности с помощью пакета Azure SDK для .NET.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: e588499a789fc5e7da7eb51009f97090ca75e562
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916605"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a>Проверка подлинности с помощью пакета Azure SDK для .NET

## <a name="recommended-azureidentity"></a>Рекомендация: Azure.Identity

Новейшие пакеты в пакете Azure SDK для .NET используют для проверки подлинности общий пакет `Azure.Identity`. Именно этот пакет `Azure.Identity` является рекомендуемым по сравнению с другими механизмами проверки подлинности, описанными далее в этом документе. Идентификаторы пакетов, поддерживающие учетные данные, предоставленные `Azure.Identity`, создаются поверх `Azure.Core` и начинаются с *Azure*. [См. список пакетов](packages.md), в котором представлены сведения об инвентаризации пакетов, использующих `Azure.Core`.

Полные инструкции по использованию `Azure.Identity` в проекте см. в документации по [клиенту Azure Identity для .NET](/dotnet/api/overview/azure/identity-readme).

> [!TIP]
> Примеры использования Azure Identity для управления ресурсами Azure и доступа к ним см. в статье с [примерами пакетов для Azure Identity, управления ресурсами и хранилища](/samples/dotnet/samples/azure-identity-resource-management-storage/).

Сведения о проверке подлинности с помощью библиотек, которые не поддерживают Azure.Identity, см. в оставшейся части этого раздела.

## <a name="access-azure-resources"></a>Оценка ресурсов Azure

Для взаимодействия с ресурсами Azure, например при получении секрета из Key Vault или сохранении BLOB-объекта в хранилище, многим библиотекам служб Azure требуется строка подключения или ключи для проверки подлинности. Например, База данных SQL использует [стандартную строку подключения SQL](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core). Строки подключения службы используются в других службах Azure, таких как [Cosmos DB](/azure/cosmos-db/), [Кэш Azure для Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache) и [Служебная шина Azure](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues). Эти строки можно получить, воспользовавшись порталом Azure, CLI или PowerShell. Также с помощью библиотек управления Azure для .NET можно выполнять запросы к ресурсам для создания строк подключения в коде.

Методы использования строки подключения зависят от продукта. [См. документацию по продукту Azure](/azure/?product=featured).

## <a name="manage-azure-resources"></a>Управление ресурсами Azure

[!include[Create service principal](includes/create-sp.md)]

После создания субъекта-службы выполнить аутентификацию субъекта-службы для создания и администрирования ресурсов можно двумя способами.

Для обоих вариантов необходимо добавить следующие пакеты NuGet в проект.

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a>Аутентификация с использованием учетных данных токена

Первый способ — создание объекта учетных данных токена в коде. Учетные данные следует безопасно хранить в файле конфигурации, реестре или Azure Key Vault.

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

При создании субъекта-службы используйте значения *clientId*, *clientSecret* и *tenantId* из выходных данных JSON.

Затем создайте точку входа объекта `Azure`, чтобы приступить к работе с API:

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

В объекте `Azure` рекомендуется явно указать *subscriptionId* из выходных данных JSON:

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithSubscription(subscriptionId);
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a>Аутентификация на основе файла

Аутентификация на основе файла позволяет поместить учетные данные субъекта-службы в текстовый файл и защитить его в файловой системе.

[!include[File-based authentication](includes/file-based-auth.md)]

Прочтите содержимое файла и создайте точку входа объекта `Azure`, чтобы приступить к работе с API:

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
