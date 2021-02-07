---
description: 'Дополнительные сведения о: Чаннелпулсеттингс'
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: b08c5483e7a0c918393795b4608b9eef16b18341
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757687"
---
# <a name="channelpoolsettings"></a>ChannelPoolSettings

ChannelPoolSettings  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс ChannelPoolSettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс ChannelPoolSettings имеет следующие свойства.  
  
### <a name="idletimeout"></a>IdleTimeout  

 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### <a name="leasetimeout"></a>LeaseTimeout  

 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время ожидания завершения операции аренды.  
  
### <a name="maxoutboundchannelsperendpoint"></a>MaxOutboundChannelsPerEndpoint  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число исходящих каналов для каждой конечной точки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
