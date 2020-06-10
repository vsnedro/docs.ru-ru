---
title: Практическое руководство. Согласованное обращение к сертификатам X.509
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: c13dd5ebb18df62ce64fc74da53f3f5a2e8cadb7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599091"
---
# <a name="how-to-consistently-reference-x509-certificates"></a>Практическое руководство. Согласованное обращение к сертификатам X.509
Существует несколько способов идентификации сертификата: с помощью хэша сертификата, имени поставщика и серийного номера, а также идентификатора ключа субъекта (SKI). Идентификатор ключа субъекта (SKI) обеспечивает уникальную идентификацию открытого ключа субъекта сертификата, поэтому он часто используется при работе с цифровой подписью XML. Значение SKI обычно является частью сертификата X. 509 как *расширение сертификата x. 509*. Windows Communication Foundation (WCF) имеет *стиль ссылок* по умолчанию, который использует поставщик и серийный номер, если в сертификате отсутствует расширение Ski. Если в сертификате имеется расширение идентификатора ключа субъекта (SKI), стиль ссылки по умолчанию использует его для указания на сертификат. Если при разработке приложения вы переходите от использования сертификатов, которые не используют расширение SKI, для сертификатов, использующих расширение SKI, также изменяется стиль ссылок, используемый в сообщениях, созданных WCF.  
  
 Если требуется согласованный стиль ссылки независимо от наличия расширения идентификатора ключа субъекта (SKI), необходимый стиль ссылки можно настроить, как показано в следующем примере кода.  
  
## <a name="example"></a>Пример  
 В следующем примере кода создается пользовательский элемент привязки безопасности, использующий единый согласованный стиль ссылки с именем издателя и серийным номером.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для компиляции кода требуются следующие пространства имен.  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a>Дополнительно

- [Работа с сертификатами](working-with-certificates.md)
