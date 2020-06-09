---
title: WCF и WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: df4a251eb5a570c9fedf19d385a027e23481afed
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594950"
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
