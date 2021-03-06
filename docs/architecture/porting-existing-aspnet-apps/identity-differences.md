---
title: Сравнение ASP.NET Identity и ASP.NET Core удостоверений
description: В этом разделе рассматриваются различия между ASP.NET Identity и ASP.NET Core удостоверениями, которые особенно важны при планировании миграции с платформа .NET Framework на .NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 184c0e7c872b7676530b917727f380d6735ba10a
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401762"
---
# <a name="compare-aspnet-identity-and-aspnet-core-identity"></a>Сравнение ASP.NET Identity и ASP.NET Core удостоверений

В ASP.NET MVC функции идентификации обычно настраиваются в *IdentityConfig.CS* в папке *App_Start* . Ознакомьтесь с тем, как это настроить в существующем приложении, и сравните его с [конфигурацией, необходимой для ASP.NET Core удостоверения](/aspnet/core/security/authentication/identity-configuration) в *Startup.CS*.

ASP.NET Identity — это API, который поддерживает функции входа в интерфейс пользователя и управляет пользователями, паролями, данными профилирования, ролями, утверждениями, маркерами, подтверждениями по электронной почте и т. д. Он поддерживает внешние поставщики входа в систему, такие как Facebook, Google, Microsoft и Twitter.

Если приложение ASP.NET MVC использует членство в ASP.NET, вы найдете инструкции по [переносу из ASP.NET членства с проверкой подлинности в удостоверение ASP.NET Core 2,0](/aspnet/core/migration/proper-to-2x/membership-to-core-identity). Это, в первую очередь, упражнение по переносу данных, при котором вы сможете использовать удостоверение ASP.NET Core с перенесенными записями пользователей.

Если вы переносите ASP.NET Identity пользователей на ASP.NET Core Identity, может потребоваться обновить хэши паролей или определить, какие пароли хэшированы с помощью нового подхода ASP.NET Core идентификации или более старого ASP.NET Identity. [Этот подход, описанный в Stack overflow](https://stackoverflow.com/a/57074910/13729) , предоставляет несколько вариантов для переноса хэшей паролей пользователей с течением времени, а не всего за один раз.

Одно из крупнейших различий в том, что ASP.NET Core удостоверение по сравнению с ASP.NET Identity, — это немало кода, который нужно включить в проект. ASP.NET Core удостоверение теперь поставляется как библиотека классов Razor, то есть все его интерфейсы и логика доступны из пакета NuGet. Существующий пользовательский интерфейс и логику можно переопределить путем [формирования шаблонов ASP.NET Core файлов удостоверений](/aspnet/core/security/authentication/scaffold-identity) , но даже в этом случае необходимо только сформировать страницы, которые нужно изменить, а не все существующие.

## <a name="migrate-from-owin--katana"></a>Миграция из OWIN или Katana

В следующих ресурсах представлены некоторые рекомендации по миграции из OWIN/Katana.

- [Миграция](/aspnet/core/migration/proper-to-2x/#globalasax-file-replacement)
- [Katana в ASPNET 5](https://devblogs.microsoft.com/aspnet/katana-asp-net-5-and-bridging-the-gap/)

## <a name="references"></a>Ссылки

- [Перенесите проверку подлинности и удостоверение в ASP.NET Core](/aspnet/core/migration/identity)
- [Введение в удостоверение на ASP.NET Core](/aspnet/core/security/authorization/introduction)
- [Настройка удостоверения ASP.NET Core](/aspnet/core/security/authentication/identity-configuration)
- [Удостоверение шаблона в ASP.NET Core проектах](/aspnet/core/security/authentication/scaffold-identity)

>[!div class="step-by-step"]
>[Назад](authentication-differences.md)
>[Вперед](controller-differences.md)
