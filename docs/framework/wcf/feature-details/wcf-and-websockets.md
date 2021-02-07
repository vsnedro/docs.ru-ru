---
description: 'Дополнительные сведения: WCF и WebSockets'
title: WCF и WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: 6b0d8c33000a65bf3bbf834f66119d65768b3cb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755984"
---
# <a name="wcf-and-websockets"></a>WCF и WebSockets

В .NET Framework версии 4.5 добавлена поддержка WebSockets в службах Windows Communication Foundation.  WebSockets - это эффективная, основанная на стандартах технология, обеспечивающая двусторонний обмен сообщениями через стандартные HTTP-порты 80 и 443. Использование стандартных HTTP-портов позволяет WebSockets устанавливать связь по сети через посредников.  Были добавлены две стандартные привязки для поддержки обмена данными через транспорт WebSocket. <xref:System.ServiceModel.NetHttpBinding> и <xref:System.ServiceModel.NetHttpsBinding>. Параметры, относящиеся к WebSocket, можно настроить в <xref:System.ServiceModel.Channels.HttpTransportBindingElement> с помощью <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Свойства.
  
## <a name="in-this-section"></a>В этом разделе  

 [Использование NetHttpBinding](using-the-nethttpbinding.md)  
 Описывает <xref:System.ServiceModel.NetHttpBinding> и его настройку.  
  
 [Практическое руководство. Создание службы WCF, обменивающейся данными через WebSockets](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Описывает процесс создания службы WCF, обменивающейся данными через Websockets.  
  
## <a name="reference"></a>Справочник  
  
## <a name="related-sections"></a>Связанные разделы
