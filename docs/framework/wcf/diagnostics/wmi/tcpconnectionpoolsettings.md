---
description: 'Дополнительные сведения о: Ткпконнектионпулсеттингс'
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 927fcba7f94bcbfa80e06479e79bf20986a661e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715201"
---
# <a name="tcpconnectionpoolsettings"></a>TcpConnectionPoolSettings

TcpConnectionPoolSettings  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс TcpConnectionPoolSettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс TcpConnectionPoolSettings имеет следующие свойства.  
  
### <a name="groupname"></a>GroupName  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Имя группы пула подключений, используемого элементом привязки.  
  
### <a name="idletimeout"></a>IdleTimeout  

 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### <a name="leasetimeout"></a>LeaseTimeout  

 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время ожидания завершения выполнения операции аренды.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число исходящих подключений для каждой конечной точки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
