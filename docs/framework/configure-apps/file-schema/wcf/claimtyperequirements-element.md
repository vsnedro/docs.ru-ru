---
title: <claimTypeRequirements> - элемент
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 6a4e5da3bd3ef6977d6258190d397130b33eb56c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148975"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="4a17f-102">Элемент \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="4a17f-102">\<claimTypeRequirements> element</span></span>

<span data-ttu-id="4a17f-103">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="4a17f-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="4a17f-104">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="4a17f-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="4a17f-105">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="4a17f-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="4a17f-106">Каждый дочерний элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4a17f-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="4a17f-107">Требование типа утверждения состоит из универсального кода ресурса (URI) типа утверждения, запрашиваемого в выданном маркере, и логического параметра, который определяет, является ли обязательным этот тип утверждения в выданном маркере.</span><span class="sxs-lookup"><span data-stu-id="4a17f-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a17f-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a17f-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4a17f-109">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="4a17f-109">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4a17f-110">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="4a17f-110">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="4a17f-111">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="4a17f-111">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="4a17f-112">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="4a17f-112">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-claimtyperequirements.md)
- [<span data-ttu-id="4a17f-113">Привязки</span><span class="sxs-lookup"><span data-stu-id="4a17f-113">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4a17f-114">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="4a17f-114">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4a17f-115">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="4a17f-115">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="4a17f-116">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4a17f-116">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="4a17f-117">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="4a17f-117">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
