---
title: TCP-UDP
description: Узнайте, как классы TcpClient, TcpListener и UdpClient обрабатывают службы TCP и UDP, которые хранят сведения о передаче данных в .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
ms.openlocfilehash: b5b8b5cb3ce38fcff9115b2f9acf23fc5a970adf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239450"
---
# <a name="tcp-udp"></a>TCP-UDP

Приложения могут использовать службы TCP и UDP с классами <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> и <xref:System.Net.Sockets.UdpClient>. Эти классы протоколов основаны на классе <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> и управляют различными аспектами передачи данных.  
  
 Классы протоколов используют синхронные методы класса **Socket** для обеспечения простого доступа к сетевым службам без накладных расходов, связанных с сохранением сведений о состоянии. При этом также не требуется знать особенности настройки сокетов для определенного протокола. Для использования асинхронных методов **Socket** можно применять асинхронные методы, предоставляемые классом <xref:System.Net.Sockets.NetworkStream>. Для доступа к возможностям класса **Socket**, которые не предоставляются классами протоколов, необходимо использовать класс **Socket**.  
  
 **TcpClient** и **TcpListener** представляют сеть с помощью класса **NetworkStream**. С помощью метода <xref:System.Net.Sockets.TcpClient.GetStream%2A> возвращается сетевой поток, после чего вызываются методы <xref:System.Net.Sockets.NetworkStream.Read%2A> и <xref:System.Net.Sockets.NetworkStream.Write%2A> потока. Базовый сокет классов протоколов не принадлежит классу **NetworkStream**, поэтому закрытие этого класса не влияет на сокет.  
  
 Класс **UdpClient** использует массив байтов для хранения датаграммы UDP. С помощью метода <xref:System.Net.Sockets.UdpClient.Send%2A> данные отправляются в сеть, а с помощью метода <xref:System.Net.Sockets.UdpClient.Receive%2A> принимается входящая датаграмма.  
  
## <a name="see-also"></a>См. также

- [Использование служб TCP](using-tcp-services.md)
- [Использование служб UDP](using-udp-services.md)
- [Использование потоков в сети](using-streams-on-the-network.md)
- [Использование асинхронных сокетов сервера](using-an-asynchronous-server-socket.md)
- [Использование асинхронных сокетов клиента](using-an-asynchronous-client-socket.md)
- [Использование протоколов приложений](using-application-protocols.md)
