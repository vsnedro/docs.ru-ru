---
title: Сравнение веб-API ASP.NET 2 и ASP.NET Core
description: Чем веб-интерфейсы API отличаются от приложений веб-API ASP.NET 2 и ASP.NET Core приложений?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 93aa917174bce24fdf924f6372312c3972473289
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401684"
---
# <a name="compare-aspnet-web-api-2-and-aspnet-core"></a>Сравнение веб-API ASP.NET 2 и ASP.NET Core

ASP.NET Core предлагает итеративные улучшения веб-API ASP.NET 2, но должны быть знакомы разработчикам, использующим веб-API 2. Веб-API ASP.NET 2 была разработана и поставляться вместе с ASP.NET MVC. Это означало, что у двух подходов существовали похожие и различные подходы к тому, как маршрутизация атрибутов и внедрение зависимостей. В ASP.NET Core больше нет различий между MVC и веб-API. Существует только ASP.NET MVC, который включает поддержку сценариев на основе представлений, конечных точек API и Razor Pages (и других вариантов, таких как проверки работоспособности и SignalR).

В дополнение к согласованности и объединению в ASP.NET Core интерфейсы API, встроенные в .NET Core, гораздо проще в тестировании, чем на основе веб-API ASP.NET 2. В настоящее время мы рассмотрим более подробное [тестирование различий](testing-differences.md) . Встроенная поддержка размещения ASP.NET Core приложений на тестовом узле, которая может создать `HttpClient` , которая делает запросы в памяти приложению, является огромным преимуществом при автоматическом тестировании.

При переходе с веб-API ASP.NET 2 на ASP.NET Core переход выполняется просто. Если у вас есть крупные контроллеры с чрезмерным прегрузкой, один из подходов к разбиению на них заключается в использовании пакетов NuGet [ардалис. апиендпоинтс](https://www.nuget.org/packages/Ardalis.ApiEndpoints/) . Этот пакет разбивает каждую конечную точку на отдельный конкретный класс с соответствующими типами запросов и ответов. Такой подход дает многие [преимущества, чем Razor Pages предложение по сравнению с кодом на основе представления](comparing-razor-pages-aspnet-mvc.md).

## <a name="references"></a>Ссылки

- [Переход с веб-API ASP.NET на ASP.NET Core](/aspnet/core/migration/webapi)
- [Пакет NuGet ардалис. Апиендпоинтс](https://www.nuget.org/packages/Ardalis.ApiEndpoints/)

>[!div class="step-by-step"]
>[Назад](comparing-razor-pages-aspnet-mvc.md)
>[Вперед](authentication-differences.md)
