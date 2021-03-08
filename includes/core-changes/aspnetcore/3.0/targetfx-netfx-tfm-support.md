---
ms.openlocfilehash: 73bf0ba78e2986da3e0aa66d492f1765df563b27
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102109127"
---
### <a name="target-framework-net-framework-support-dropped"></a>Целевая платформа: прекращена поддержка .NET Framework

Начиная с ASP.NET Core 3.0, .NET Framework больше поддерживается как целевая платформа.

#### <a name="change-description"></a>Описание изменений

.NET Framework 4.8 — это последняя основная версия .NET Framework. Новые приложения ASP.NET Core следует создавать на основе .NET Core. Начиная с выпуска .NET Core 3.0 вы можете считать ASP.NET Core 3.0 частью .NET Core.

Клиенты, которые используют ASP.NET Core совместно с .NET Framework, сохраняют полноценную поддержку в выпуске [.NET Core 2.1 LTS](https://dotnet.microsoft.com/download/dotnet/2.1). Поддержка и обслуживание для выпуска 2.1 сохранится по меньшей мере до 21 августа 2021 г. Это ровно три года с момента объявления выпуска LTS, в строгом соответствии с [политикой поддержки .NET](https://dotnet.microsoft.com/platform/support-policy). Поддержка пакетов ASP.NET Core 2.1 **на платформе .NET Framework** будет продолжаться неограниченное время, аналогично [политике обслуживания для других платформ ASP.NET на основе пакетов](https://dotnet.microsoft.com/platform/support/policy/aspnet).

Дополнительные сведения о переносе кода из .NET Core в .NET Framework см. в [этой статье](~/docs/core/porting/index.md).

Это изменение не коснется пакетов `Microsoft.Extensions` (сюда относятся ведение журнала, внедрение зависимостей и конфигурация) и Entity Framework Core. Для них сохраняется поддержка .NET Standard.

Дополнительные сведения о том, что привело нас в этим изменениям, см. в [исходной записи блога](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Приложения ASP.NET Core могли работать на основе .NET Core или .NET Framework.

#### <a name="new-behavior"></a>Новое поведение

Приложения ASP.NET Core версии будут выполняться только в .NET Core.

#### <a name="recommended-action"></a>Рекомендованное действие

Выполните одно из указанных ниже действий.

- Сохраните приложение в ASP.NET Core 2.1.
- Перенесите приложения и все его зависимости на .NET Core.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
