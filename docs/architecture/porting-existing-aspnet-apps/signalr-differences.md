---
title: Сравните ASP.NET SignalR и SignalR ASP.NET Core
description: Как ASP.NET Core SignalR отличается от его предшественника, ASP.NET SignalR?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 89236bd0272c8f20cf9838dddefeb9afee1f3d93
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401696"
---
# <a name="compare-aspnet-signalr-and-aspnet-core-signalr"></a>Сравните ASP.NET SignalR и SignalR ASP.NET Core

ASP.NET Core SignalR несовместим с клиентами или серверами, использующими SignalR ASP.NET. Необходимо обновить клиенты и сервер, чтобы они использовали ASP.NET Core SignalR. Некоторые различия описаны в этом разделе, а полный список доступен в [документах](/aspnet/core/signalr/version-differences). Для ASP.NET Core SignalR требуется .NET Core 2,1 или более поздней версии.

## <a name="feature-differences"></a>Различия в функциях

- ASP.NET SignalR автоматически пытается повторно подключиться к удаленным подключениям; Это поведение является явным согласием для клиентов ASP.NET Core SignalR
- Обе платформы поддерживают JSON; ASP.NET Core SignalR также поддерживает двоичный протокол на основе MessagePack, а также могут быть созданы пользовательские протоколы.
- Непостоянное движение кадров, поддерживаемое ASP.NET SignalR, не поддерживается в ASP.NET Core SignalR.
- ASP.NET Core SignalR необходимо настроить, добавив `services.AddSignalR()` `app.UseEndpoints` в `Startup.ConfigureServices` и `Startup.Configure` соответственно.
- Для ASP.NET Core SignalR требуются прикрепленные сеансы; ASP.NET SignalR нет.
- ASP.NET Core упрощает модель подключения; подключения выполняются только в одном концентраторе.
- ASP.NET Core SignalR поддерживает потоковую передачу данных от концентратора клиенту.
- ASP.NET Core SignalR не поддерживает передачу состояния между клиентами и концентратором.
- `PersistentConnection`Класс не существует в ASP.NET Core SignalR.
- ASP.NET SignalR поддерживает SQL Server и Redis. ASP.NET Core SignalR поддерживает [Azure SignalR](/azure/azure-signalr/) и Redis.

## <a name="references"></a>Ссылки

- [Различия между ASP.NET SignalR и SignalR ASP.NET Core](/aspnet/core/signalr/version-differences)
- [Служба SignalR Azure](/azure/azure-signalr/)

>[!div class="step-by-step"]
>[Назад](razor-differences.md)
>[Вперед](testing-differences.md)
