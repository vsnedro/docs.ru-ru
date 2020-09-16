---
title: Форматы метаданных
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: a304b6026ae9b8bc9506bfa82ab6eaa3c80b2a42
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679381"
---
# <a name="metadata-formats"></a>Форматы метаданных

Windows Communication Foundation (WCF) поддерживает форматы метаданных, приведенные в следующей таблице.  
  
## <a name="metadata-specifications-and-usage"></a>Спецификации и использование метаданных  
  
|Протокол|Спецификация и использование|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> Для описания служб WCF использует язык описания веб-служб (WSDL).|  
|схема XML|[XML-схема, часть 2: типы типа «второй выпуск](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) » и « [схема XML», часть 1. Вторая выпускная структура](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF использует схему XML для описания типов данных, используемых в сообщениях.|  
|WS Policy|[Web Services Policy 1.2 - платформа (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Web Services Policy 1.5 - платформа](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF использует спецификации WS-Policy 1,2 или 1,5 с утверждениями, зависящими от домена, для описания требований и возможностей службы.|  
|Вложения WS Policy|[Web Services Policy 1.2 - вложение (WS-PolicyAttachment)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF реализует вложения WS-Policy для присоединения выражений политики в различных областях в WSDL.|  
|WS Metadata Exchange|[Обмен метаданными веб-служб (WS-MetadataExchange)](https://www.w3.org/TR/ws-metadata-exchange/)<br /><br /> WCF реализует WS-MetadataExchange для получения схемы XML, WSDL и WS-Policy.|  
|Привязка WS Addressing для WSDL|[Web Services Addressing 1.0 - привязка WSDL](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF реализует привязку WS-Addressing для WSDL, чтобы присоединить сведения об адресации в WSDL.|  
  
## <a name="see-also"></a>См. также

- [Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL и политика](wsdl-and-policy.md)
