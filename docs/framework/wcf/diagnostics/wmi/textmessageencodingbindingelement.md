---
description: 'Дополнительные сведения о: Текстмессажеенкодингбиндинжелемент'
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 9848f1660642f92c4bce3542fbd404f463b8c84d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757349"
---
# <a name="textmessageencodingbindingelement"></a>TextMessageEncodingBindingElement

TextMessageEncodingBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс TextMessageEncodingBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс TextMessageEncodingBindingElement имеет следующие свойства.  
  
### <a name="encoding"></a>Кодирование  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Кодировка, используемая при отправке сообщений через привязку.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.  
  
### <a name="readerquotas"></a>ReaderQuotas  

 Тип данных: XmlDictionaryReaderQuotas  
  
 Тип доступа: только для чтения  
  
 Квоты средств чтения.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
