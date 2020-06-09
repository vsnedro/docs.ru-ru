---
title: Различия проверки сертификатов службы с использованием Internet Explorer и WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 151075f2894b895ab90418748df9face3aa70252
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599195"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Различия проверки сертификатов службы с использованием Internet Explorer и WCF
Из-за различий между способом проверки сертификатов служб Internet Explorer и Windows Communication Foundation (WCF) при использовании протокола HTTPS Internet Explorer может получить доступ к странице справки или языку WSDL службы, даже если клиент WCF может успешно отправить сообщения в конечные точки службы. Это происходит потому, что Internet Explorer проверяет, имеет ли сертификат службы `ServerAuthentication` идентификаторы объектов (OID) в расширенных флагах использования, тогда как WCF не применяет такое ограничение. Если Internet Explorer не может получить доступ к странице справки службы или WSDL для службы, используйте [средство служебной программы для метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданным службы.  
  
## <a name="see-also"></a>Дополнительно

- [Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Практическое руководство. Извлечение данных и реализация совместимой службы](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
