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
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="c48d7-102">Различия проверки сертификатов службы с использованием Internet Explorer и WCF</span><span class="sxs-lookup"><span data-stu-id="c48d7-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="c48d7-103">Из-за различий между способом проверки сертификатов служб Internet Explorer и Windows Communication Foundation (WCF) при использовании протокола HTTPS Internet Explorer может получить доступ к странице справки или языку WSDL службы, даже если клиент WCF может успешно отправить сообщения в конечные точки службы.</span><span class="sxs-lookup"><span data-stu-id="c48d7-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="c48d7-104">Это происходит потому, что Internet Explorer проверяет, имеет ли сертификат службы `ServerAuthentication` идентификаторы объектов (OID) в расширенных флагах использования, тогда как WCF не применяет такое ограничение.</span><span class="sxs-lookup"><span data-stu-id="c48d7-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="c48d7-105">Если Internet Explorer не может получить доступ к странице справки службы или WSDL для службы, используйте [средство служебной программы для метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданным службы.</span><span class="sxs-lookup"><span data-stu-id="c48d7-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c48d7-106">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c48d7-106">See also</span></span>

- [<span data-ttu-id="c48d7-107">Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP</span><span class="sxs-lookup"><span data-stu-id="c48d7-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="c48d7-108">Практическое руководство. Извлечение данных и реализация совместимой службы</span><span class="sxs-lookup"><span data-stu-id="c48d7-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
