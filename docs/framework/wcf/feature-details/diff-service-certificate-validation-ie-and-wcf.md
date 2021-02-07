---
description: Дополнительные сведения см. в статье различия между проверкой сертификата службы, выполненной с помощью Internet Explorer и WCF.
title: Различия проверки сертификатов службы с использованием Internet Explorer и WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 2d635aec0949ec4e65cd965089206bbf6d6815a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756361"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Различия проверки сертификатов службы с использованием Internet Explorer и WCF

Из-за различий между способом проверки сертификатов служб Internet Explorer и Windows Communication Foundation (WCF) при использовании протокола HTTPS Internet Explorer может получить доступ к странице справки или языку WSDL службы, даже если клиент WCF может успешно отправить сообщения в конечные точки службы. Это происходит потому, что Internet Explorer проверяет, имеет ли сертификат службы `ServerAuthentication` идентификаторы объектов (OID) в расширенных флагах использования, тогда как WCF не применяет такое ограничение. Если Internet Explorer не может получить доступ к странице справки службы или WSDL для службы, используйте [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданным службы.  
  
## <a name="see-also"></a>См. также

- [Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Практическое руководство. Извлечение данных и реализация совместимой службы](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
