---
title: Различия в размещении между ASP.NET MVC и ASP.NET Core
description: Обзор различий между размещением приложений ASP.NET MVC и ASP.NET Core приложениями.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 402dd5782cb215545ff2ef13f97ec269b8a2540b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401768"
---
# <a name="hosting-differences-between-aspnet-mvc-and-aspnet-core"></a>Различия в размещении между ASP.NET MVC и ASP.NET Core

Приложения ASP.NET MVC размещаются в IIS и могут полагаться на конфигурацию IIS для их поведения. Это часто включает [модули IIS](/iis/get-started/introduction-to-iis/iis-modules-overview). В рамках проверки приложения, чтобы подготовиться к его переносу из ASP.NET MVC в ASP.NET Core, команды должны выбрать, какие модули, если они используются, из списка модулей IIS, установленных на сервере.

[ASP.NET Core приложения могут выполняться на нескольких разных серверах](/aspnet/core/fundamentals/servers/). По умолчанию для кросс-платформенного сервера Kestrel является хорошим выбором. Приложения, работающие в Kestrel, могут размещаться в службах IIS, выполняющихся в отдельном процессе. В Windows приложения также могут выполняться в процессе в службах IIS или с помощью HTTP.sys. Как правило, для оптимальной производительности рекомендуется Kestrel. HTTP.sys можно использовать в сценариях, где приложение имеет доступ к Интернету и необходимые возможности поддерживаются HTTP.sys, но не Kestrel.

Kestrel не имеет эквивалента модулям IIS (хотя приложения, размещенные в IIS, по-прежнему могут использовать преимущества модулей IIS). Для достижения эквивалентного поведения обычно используется промежуточный слой, настроенный в самом приложении ASP.NET Core.

## <a name="references"></a>Ссылки

- [Модули IIS](/iis/get-started/introduction-to-iis/iis-modules-overview)
- [Серверы ASP.NET Core](/aspnet/core/fundamentals/servers/)

>[!div class="step-by-step"]
>[Назад](app-startup-differences.md)
>[Вперед](serving-static-files.md)
