---
title: Расширение безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: d91f4812dbccb7807be2e0780cccd1d0c38b1f40
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273065"
---
# <a name="extending-security"></a><span data-ttu-id="83765-102">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="83765-102">Extending Security</span></span>

<span data-ttu-id="83765-103">Для поддержки новых типов утверждений и пользовательских маркеров можно расширить инфраструктуру безопасности Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="83765-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="83765-104">Это подробно описывается в следующих подразделах.</span><span class="sxs-lookup"><span data-stu-id="83765-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83765-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="83765-105">In This Section</span></span>  
  
 [<span data-ttu-id="83765-106">Пользовательские учетные данные и проверка учетных данных</span><span class="sxs-lookup"><span data-stu-id="83765-106">Custom Credential and Credential Validation</span></span>](custom-credential-and-credential-validation.md)  
 <span data-ttu-id="83765-107">Рассматривается, как модель удостоверения используется при проверке пользовательских учетных данных.</span><span class="sxs-lookup"><span data-stu-id="83765-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="83765-108">Пользовательские маркеры</span><span class="sxs-lookup"><span data-stu-id="83765-108">Custom Tokens</span></span>](custom-tokens.md)  
 <span data-ttu-id="83765-109">Маркеры, выдаваемые службой маркеров безопасности (STS), - обычно маркеры SAML.</span><span class="sxs-lookup"><span data-stu-id="83765-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="83765-110">В этом разделе описывается, как создать тип пользовательского маркера.</span><span class="sxs-lookup"><span data-stu-id="83765-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="83765-111">Пользовательская авторизация</span><span class="sxs-lookup"><span data-stu-id="83765-111">Custom Authorization</span></span>](custom-authorization.md)  
 <span data-ttu-id="83765-112">Объясняется, как реализовать пользовательскую авторизацию.</span><span class="sxs-lookup"><span data-stu-id="83765-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="83765-113">Переопределение идентификатора службы для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="83765-113">Overriding the Identity of a Service for Authentication</span></span>](overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="83765-114">Описывается, как переопределить идентификацию службы для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="83765-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="83765-115">Практическое руководство. Создание пользовательского средства проверки идентификации клиентов</span><span class="sxs-lookup"><span data-stu-id="83765-115">How to: Create a Custom Client Identity Verifier</span></span>](how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="83765-116">Демонстрирует, как проверить идентификацию пользовательской конечной точки.</span><span class="sxs-lookup"><span data-stu-id="83765-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="83765-117">Практическое руководство. Использование отдельных сертификатов X.509 для подписывания и шифрования</span><span class="sxs-lookup"><span data-stu-id="83765-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="83765-118">Обычно сообщения подписываются и шифруются одним сертификатом.</span><span class="sxs-lookup"><span data-stu-id="83765-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="83765-119">В этом разделе объясняется, как при необходимости использовать два сертификата.</span><span class="sxs-lookup"><span data-stu-id="83765-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="83765-120">Практическое руководство. Изменение поставщика служб шифрования для закрытого ключа сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="83765-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="83765-121">Объясняет, как изменить поставщик служб шифрования, используемый для предоставления закрытого ключа сертификата X. 509, и как интегрировать поставщик в платформу Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="83765-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="83765-122">Справочник</span><span class="sxs-lookup"><span data-stu-id="83765-122">Reference</span></span>  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="83765-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="83765-123">Related Sections</span></span>  

 [<span data-ttu-id="83765-124">Безопасность</span><span class="sxs-lookup"><span data-stu-id="83765-124">Security</span></span>](../feature-details/security.md)  
  
 [<span data-ttu-id="83765-125">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="83765-125">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="83765-126">См. также</span><span class="sxs-lookup"><span data-stu-id="83765-126">See also</span></span>

- [<span data-ttu-id="83765-127">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="83765-127">Security Overview</span></span>](../feature-details/security-overview.md)
