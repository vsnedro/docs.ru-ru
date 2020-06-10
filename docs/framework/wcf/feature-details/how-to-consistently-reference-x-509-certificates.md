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
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="33074-102">Практическое руководство. Согласованное обращение к сертификатам X.509</span><span class="sxs-lookup"><span data-stu-id="33074-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="33074-103">Существует несколько способов идентификации сертификата: с помощью хэша сертификата, имени поставщика и серийного номера, а также идентификатора ключа субъекта (SKI).</span><span class="sxs-lookup"><span data-stu-id="33074-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="33074-104">Идентификатор ключа субъекта (SKI) обеспечивает уникальную идентификацию открытого ключа субъекта сертификата, поэтому он часто используется при работе с цифровой подписью XML.</span><span class="sxs-lookup"><span data-stu-id="33074-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="33074-105">Значение SKI обычно является частью сертификата X. 509 как *расширение сертификата x. 509*.</span><span class="sxs-lookup"><span data-stu-id="33074-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="33074-106">Windows Communication Foundation (WCF) имеет *стиль ссылок* по умолчанию, который использует поставщик и серийный номер, если в сертификате отсутствует расширение Ski.</span><span class="sxs-lookup"><span data-stu-id="33074-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="33074-107">Если в сертификате имеется расширение идентификатора ключа субъекта (SKI), стиль ссылки по умолчанию использует его для указания на сертификат.</span><span class="sxs-lookup"><span data-stu-id="33074-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="33074-108">Если при разработке приложения вы переходите от использования сертификатов, которые не используют расширение SKI, для сертификатов, использующих расширение SKI, также изменяется стиль ссылок, используемый в сообщениях, созданных WCF.</span><span class="sxs-lookup"><span data-stu-id="33074-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="33074-109">Если требуется согласованный стиль ссылки независимо от наличия расширения идентификатора ключа субъекта (SKI), необходимый стиль ссылки можно настроить, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="33074-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33074-110">Пример</span><span class="sxs-lookup"><span data-stu-id="33074-110">Example</span></span>  
 <span data-ttu-id="33074-111">В следующем примере кода создается пользовательский элемент привязки безопасности, использующий единый согласованный стиль ссылки с именем издателя и серийным номером.</span><span class="sxs-lookup"><span data-stu-id="33074-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="33074-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="33074-112">Compiling the Code</span></span>  
 <span data-ttu-id="33074-113">Для компиляции кода требуются следующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="33074-113">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="33074-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="33074-114">See also</span></span>

- [<span data-ttu-id="33074-115">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="33074-115">Working with Certificates</span></span>](working-with-certificates.md)
