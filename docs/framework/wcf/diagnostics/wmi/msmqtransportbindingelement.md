---
description: 'Дополнительные сведения о: Мсмктранспортбиндинжелемент'
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 4b6f363d979972c6ff0a2a378906feeece2ff6b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803156"
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement

MsmqTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс MsmqTransportBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс MsmqTransportBindingElement имеет следующие свойства.  
  
### <a name="maxpoolsize"></a>MaxPoolSize  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальный размер пула, содержащего внутренние объекты сообщений MSMQ.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Значение перечисления, в котором указывается поставленный в очередь транспорт канала связи, используемый данной привязкой.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Возвращает логическое значение, указывающее, следует ли преобразовывать адреса очередей с помощью Active Directory.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
