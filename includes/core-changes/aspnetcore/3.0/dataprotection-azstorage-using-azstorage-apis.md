---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032737"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a>Защита данных. DataProtection.Blobs использует новые API службы хранилища Azure

`Azure.Extensions.AspNetCore.DataProtection.Blobs` зависит от [библиотек службы хранилища Azure](https://github.com/Azure/azure-storage-net). Эти библиотеки переименовали свои сборки, пакеты и пространства имен. Начиная с ASP.NET Core 3.0, `Azure.Extensions.AspNetCore.DataProtection.Blobs` использует новые API и пакеты с префиксом `Azure.Storage.`.

Если у вас возникли вопросы об API службы хранилища Azure, см. страницу <https://github.com/Azure/azure-storage-net>. Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Пакет ссылался на пакет `WindowsAzure.Storage` NuGet.
Пакет ссылается на пакет `Microsoft.Azure.Storage.Blob` NuGet.

#### <a name="new-behavior"></a>Новое поведение

Пакет ссылается на пакет `Azure.Storage.Blob` NuGet.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение позволяет `Azure.Extensions.AspNetCore.DataProtection.Blobs` переходить к рекомендуемым пакетам службы хранилища Azure.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вам по-прежнему нужно использовать старые API службы хранилища Azure с ASP.NET Core 3.0, добавьте прямую зависимость в пакет [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) или [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/). Этот пакет можно установить вместе с новыми API `Azure.Storage`.

Во многих случаях обновление включает только изменение инструкций `using` для использования новых пространств имен:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
