---
description: 'Дополнительные сведения о: TransportBindingElement'
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: de08feaf8abec3a0dfee97e92d68d5223cd0de44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757115"
---
# <a name="transportbindingelement"></a>TransportBindingElement

TransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс TransportBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс TransportBindingElement имеет следующие свойства.  
  
### <a name="manualaddressing"></a>ManualAddressing  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, требуется ли пользователю контролировать адресацию сообщений.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  

 Тип данных: sint64  
  
 Тип доступа: только для чтения  
  
 Максимальный размер буферного пула для этой привязки.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  

 Тип данных: sint64  
  
 Тип доступа: только для чтения  
  
 Максимально размер сообщения, обрабатываемого данной привязкой.  
  
### <a name="scheme"></a>Схема  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Схема универсального кода ресурса (URI) для транспорта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.TransportBindingElement>
