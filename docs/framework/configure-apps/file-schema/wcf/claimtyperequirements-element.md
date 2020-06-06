---
title: <claimTypeRequirements> - элемент
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: b4d8479dd9a24774afbd0549caf9e261f55fa147
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "69926141"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="a06df-102">Элемент \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="a06df-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="a06df-103">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="a06df-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="a06df-104">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="a06df-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="a06df-105">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="a06df-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="a06df-106">Каждый дочерний элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="a06df-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="a06df-107">Требование типа утверждения состоит из универсального кода ресурса (URI) типа утверждения, запрашиваемого в выданном маркере, и логического параметра, который определяет, является ли обязательным этот тип утверждения в выданном маркере.</span><span class="sxs-lookup"><span data-stu-id="a06df-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a06df-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a06df-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a06df-109">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="a06df-109">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a06df-110">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="a06df-110">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a06df-111">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="a06df-111">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a06df-112">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="a06df-112">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-claimtyperequirements.md)
- [<span data-ttu-id="a06df-113">Привязки</span><span class="sxs-lookup"><span data-stu-id="a06df-113">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a06df-114">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="a06df-114">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a06df-115">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="a06df-115">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="a06df-116">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a06df-116">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="a06df-117">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="a06df-117">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
