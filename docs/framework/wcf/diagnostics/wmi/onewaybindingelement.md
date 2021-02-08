---
description: 'Дополнительные сведения о: Оневайбиндинжелемент'
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 9c2ccc301bd854c7b85fcc53551ed6def329a8fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803091"
---
# <a name="onewaybindingelement"></a>OneWayBindingElement

OneWayBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс OneWayBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс OneWayBindingElement имеет следующие свойства.  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  

 Тип данных: ChannelPoolSettings  
  
 Тип доступа: только для чтения  
  
 Параметры пула каналов.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число принимаемых каналов.  
  
### <a name="packetroutable"></a>PacketRoutable  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, возможна ли маршрутизация пакета.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
