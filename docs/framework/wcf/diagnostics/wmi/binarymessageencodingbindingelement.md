---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: eb174d12731d7f1bc78f4d709cf043daf2346bd2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269799"
---
# <a name="binarymessageencodingbindingelement"></a>BinaryMessageEncodingBindingElement

BinaryMessageEncodingBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс BinaryMessageEncodingBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс BinaryMessageEncodingBindingElement имеет следующие свойства.  
  
## <a name="maxreadpoolsize"></a>MaxReadPoolSize  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.  
  
## <a name="maxsessionsize"></a>MaxSessionSize  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее максимальный размер буфера, используемого для кодирования (в байтах).  
  
## <a name="maxwritepoolsize"></a>MaxWritePoolSize  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.  
  
## <a name="readerquotas"></a>ReaderQuotas  

 Тип данных: XmlDictionaryReaderQuotas  
  
 Тип доступа: только для чтения  
  
 Квоты средств чтения.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
