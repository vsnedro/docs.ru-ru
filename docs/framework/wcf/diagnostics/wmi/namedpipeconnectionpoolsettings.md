---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8422e1adf9a8914b631431eba5c9c0ed058cd0f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258027"
---
# <a name="namedpipeconnectionpoolsettings"></a>NamedPipeConnectionPoolSettings

NamedPipeConnectionPoolSettings  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс NamedPipeConnectionPoolSettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс NamedPipeConnectionPoolSettings имеет следующие свойства.  
  
### <a name="groupname"></a>GroupName  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Имя группы пула подключений, используемого элементом привязки.  
  
### <a name="idletimeout"></a>IdleTimeout  

 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число исходящих соединений для каждой конечной точки на клиенте.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
