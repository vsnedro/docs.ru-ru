---
description: Дополнительные сведения о классе Channel
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: dcc92f78f09e9a73a24134c6c0685949f46f38dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757726"
---
# <a name="channel-class"></a>Класс Channel

Канал  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс Channel не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс Channel имеет следующие свойства.  
  
### <a name="localaddress"></a>LocalAddress  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Локальная конечная точка канала.  
  
### <a name="ref"></a>ref  

 Тип данных: Endpoint  
  
 Тип доступа: только для чтения  
  
 Ссылка на конечную точку, к которой подключается канал.  
  
### <a name="remoteaddress"></a>RemoteAddress  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Удаленный адрес, связанный с каналом.  
  
### <a name="sessionid"></a>SessionId  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Идентификатор текущего сеанса, если он существует.  
  
### <a name="type"></a>Тип  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Тип канала.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.ChannelBase>
