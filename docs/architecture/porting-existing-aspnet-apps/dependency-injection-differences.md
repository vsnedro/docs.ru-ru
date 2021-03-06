---
title: Различия в внедрении зависимостей между ASP.NET MVC и ASP.NET Core
description: Рассмотрим, как внедрение зависимостей работает в ASP.NET MVC и ASP.NET Core, как они отличаются и как выполнить миграцию из ASP.NET MVC в ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: aa1c7dd2f70e1a545352feb6560177bc6e2baa2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401780"
---
# <a name="dependency-injection-differences-between-aspnet-mvc-and-aspnet-core"></a>Различия в внедрении зависимостей между ASP.NET MVC и ASP.NET Core

Несмотря на то, что внедрение зависимостей (DI) не встроено в ASP.NET MVC или веб-API, многие приложения включают его, добавляя пакет NuGet с контейнером инверсии управления (IOC). Они иногда называются контейнерами DI для внедрения зависимостей (или инверсии). Ниже перечислены некоторые из наиболее популярных контейнеров, используемых в приложениях ASP.NET MVC.

- [Autofac](https://www.autofac.org/);
- [Unity](https://unitycontainer.github.io/)
- [нинжект](http://www.ninject.org/)
- [StructureMap](http://structuremap.github.io/) *(не рекомендуется)*
- [Castle Windsor](http://www.castleproject.org/projects/windsor/)

Если приложение ASP.NET MVC не использует DI, возможно, вам потребуется изучить встроенную поддержку DI в ASP.NET Core. DI способствует слабой взаимосвязи модулей в приложении и обеспечивает лучшую пригодность к тестированию и соблюдение таких принципов, как [сплошная](https://www.weeklydevtips.com/episodes/047).

Если в приложении используется DI, то, вероятно, лучше всего подойдет, если используемый контейнер поддерживает ASP.NET Core. Если это так, можно продолжить его использование и настраиваемые правила конфигурации, описывающие сопоставления типов и время существования.

В любом случае следует рассмотреть возможность использования встроенной поддержки DI, поставляемой с ASP.NET Core, так как она может соответствовать потребностям вашего приложения.

## <a name="dependency-injection-in-aspnet-core"></a>Внедрение зависимостей в ASP.NET Core

ASP.NET Core предполагает, что приложения будут использовать DI. Она не только встроена в платформу, но и необходима для поддержки функций платформы в ASP.NET Coreных приложениях. При запуске приложения выполняется вызов, `ConfigureServices` который отвечает за регистрацию всех типов, которые могут создаваться и внедряться в контейнере di (служба коллекции или поставщик служб) в приложение. Встроенные функции ASP.NET Core, такие как Entity Framework Core, идентификация и даже MVC, передаются в приложение путем их настройки в качестве служб в `ConfigureServices` методе.

В дополнение к реализации по умолчанию приложения по-прежнему могут использовать пользовательские контейнеры. В [документации описано, как заменить контейнер службы по умолчанию](../../core/extensions/dependency-injection-guidelines.md#default-service-container-replacement).

DI является фундаментальным для ASP.NET Core. Если ваша команда еще не была хорошо принята на практике, необходимо понять ее перед переносом приложения.

## <a name="references"></a>Ссылки

- [Внедрение зависимостей в .NET](../../core/extensions/dependency-injection.md)
- [Использование внедрения зависимостей в ASP.NET Core](/aspnet/core/fundamentals/dependency-injection)

>[!div class="step-by-step"]
>[Назад](serving-static-files.md)
>[Вперед](middleware-modules-handlers.md)
