---
description: 'Дополнительные сведения о: Пиртранспортбиндинжелемент'
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: b1ca8020f51a5f9b121f7d238d82b9971d13cdd4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757336"
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement

PeerTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс PeerTransportBindingElement не определяет никакие методы.  
  
## <a name="properties"></a>Свойства  

 Класс PeerTransportBindingElement имеет следующие свойства.  
  
### <a name="listenipaddress"></a>ListenIPAddress  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 IP-адрес, на котором одноранговый узел будет ожидать сообщения.  
  
### <a name="port"></a>Port  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Порт сетевого интерфейса, на котором эта привязка будет обрабатывать сообщения однорангового канала.  
  
### <a name="security"></a>Безопасность  

 Тип данных: PeerSecuritySettings  
  
 Тип доступа: только для чтения  
  
 Параметры безопасности однорангового транспорта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
