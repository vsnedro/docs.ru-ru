---
title: Аутентификация в WCF
description: Узнайте о некоторых механизмах WCF, обеспечивающих проверку подлинности, таких как проверка подлинности Windows, сертификаты X. 509, а также имя пользователя и пароль.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 4c3348cfb84b8571dc1f24b774ffcd691aaa5001
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247524"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="22ac6-103">Аутентификация в WCF</span><span class="sxs-lookup"><span data-stu-id="22ac6-103">Authentication in WCF</span></span>
<span data-ttu-id="22ac6-104">В следующих разделах представлен ряд различных механизмов в Windows Communication Foundation (WCF), которые обеспечивают проверку подлинности, например, проверка подлинности Windows, сертификаты X. 509, а также имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="22ac6-104">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22ac6-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="22ac6-105">In This Section</span></span>  
 [<span data-ttu-id="22ac6-106">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="22ac6-106">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="22ac6-107">Возможности ASP.NET включают членство и поставщик ролей, базу данных для хранения пар имя пользователя-пароль, используемых для проверки подлинности, и роли пользователя для авторизации.</span><span class="sxs-lookup"><span data-stu-id="22ac6-107">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="22ac6-108">В этом разделе объясняется, как службы WCF могут использовать одну и ту же базу данных для проверки подлинности и авторизации пользователей.</span><span class="sxs-lookup"><span data-stu-id="22ac6-108">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="22ac6-109">Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="22ac6-109">How to: Use a Custom User Name and Password Validator</span></span>](how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="22ac6-110">Демонстрируется процесс интеграции настраиваемого проверяющего элемента управления для имени пользователя/пароля.</span><span class="sxs-lookup"><span data-stu-id="22ac6-110">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="22ac6-111">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="22ac6-111">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)  
 <span data-ttu-id="22ac6-112">В качестве дополнительной защиты клиент может проверить подлинность службы, указав ожидаемое *удостоверение* службы.</span><span class="sxs-lookup"><span data-stu-id="22ac6-112">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="22ac6-113">Если ожидаемое и возвращаемое службой удостоверения не совпадают, проверку подлинности выполнить не удается.</span><span class="sxs-lookup"><span data-stu-id="22ac6-113">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="22ac6-114">Согласование безопасности и тайм-ауты</span><span class="sxs-lookup"><span data-stu-id="22ac6-114">Security Negotiation and Timeouts</span></span>](security-negotiation-and-timeouts.md)  
 <span data-ttu-id="22ac6-115">Как следует использовать свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> в классе <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="22ac6-115">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="22ac6-116">Отладка ошибок проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="22ac6-116">Debugging Windows Authentication Errors</span></span>](debugging-windows-authentication-errors.md)  
 <span data-ttu-id="22ac6-117">Основной акцент делается на общих выявленных проблемах при использовании проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="22ac6-117">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="22ac6-118">Справочник</span><span class="sxs-lookup"><span data-stu-id="22ac6-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="22ac6-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="22ac6-119">Related Sections</span></span>  
 [<span data-ttu-id="22ac6-120">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="22ac6-120">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="22ac6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="22ac6-121">See also</span></span>

- [<span data-ttu-id="22ac6-122">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="22ac6-122">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="22ac6-123">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="22ac6-123">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
