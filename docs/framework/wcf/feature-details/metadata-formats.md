---
description: Дополнительные сведения о форматах метаданных
title: Форматы метаданных
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: f8c5d6dd5c75f38d4114f6232e9d1d6048a8343e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733922"
---
# <a name="metadata-formats"></a>Форматы метаданных

Windows Communication Foundation (WCF) поддерживает форматы метаданных, приведенные в следующей таблице.  
  
## <a name="metadata-specifications-and-usage"></a>Спецификации и использование метаданных  
  
|Протокол|Спецификация и использование|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> Для описания служб WCF использует язык описания веб-служб (WSDL).|  
|схема XML|[XML-схема, часть 2: типы типа «второй выпуск](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) » и « [схема XML», часть 1. Вторая выпускная структура](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF использует схему XML для описания типов данных, используемых в сообщениях.|  
|WS Policy|[Web Services Policy 1.2 - платформа (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Web Services Policy 1.5 - платформа](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF использует спецификации WS-Policy 1,2 или 1,5 с утверждениями, зависящими от домена, для описания требований и возможностей службы.|  
|Вложения WS Policy|[Web Services Policy 1.2 - вложение (WS-PolicyAttachment)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF реализует WS-Policyные вложения для присоединения выражений политики в различных областях в WSDL.|  
|WS Metadata Exchange|[Web Services Metadata Exchange (WS-MetadataExchange) версии 1.1](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF реализует WS-MetadataExchange для получения схемы XML, WSDL и WS-Policy.|  
|Привязка WS Addressing для WSDL|[Web Services Addressing 1.0 - привязка WSDL](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF реализует WS-Addressingную привязку для WSDL, чтобы присоединить сведения об адресации в WSDL.|  
  
## <a name="see-also"></a>См. также

- [Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL и политика](wsdl-and-policy.md)
