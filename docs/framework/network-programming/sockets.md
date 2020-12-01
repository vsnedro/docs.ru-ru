---
title: сокеты
description: Узнайте о классе .NET Framework Socket, который представляет собой версию служб сокетов на основе управляемого кода, предоставляемую API Winsock32.
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
ms.openlocfilehash: e00d04164f7ce5251b7f30b5abd16c14643f6862
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263130"
---
# <a name="sockets"></a>сокеты

Пространство имен <xref:System.Net.Sockets> содержит управляемую реализацию интерфейса Windows Sockets. Все остальные классы для доступа к сети в пространстве имен <xref:System.Net> основываются на этой реализации сокетов.  
  
 Класс <xref:System.Net.Sockets.Socket> платформы .NET Framework — это версия служб сокетов на основе управляемого кода, предоставляемая API Winsock32. В большинстве случаев методы класса **Socket** просто маршалируют данные в аналогичные собственные методы Win32 и осуществляют все необходимые проверки безопасности.  
  
 Класс **Socket** поддерживает два основных режима: синхронный и асинхронный. В синхронном режиме при вызове функций, выполняющих сетевые операции (например, <xref:System.Net.Sockets.Socket.Send%2A> и <xref:System.Net.Sockets.Socket.Receive%2A>), ожидается завершение операций, прежде чем управление возвращается вызывающей программе. В асинхронном режиме вызовы возвращаются немедленно.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание сокета](how-to-create-a-socket.md)

- [Использование протоколов приложений](using-application-protocols.md)
