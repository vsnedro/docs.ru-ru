---
title: <remove> элемента <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399997"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="4fc4d-102">\<remove> элемента \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="4fc4d-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="4fc4d-103">Указывает типы утверждений в федеративных учетных данных, которые должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="4fc4d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fc4d-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fc4d-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4fc4d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4fc4d-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fc4d-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4fc4d-107">Attributes</span></span>  
  
|<span data-ttu-id="4fc4d-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4fc4d-108">Attribute</span></span>|<span data-ttu-id="4fc4d-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="4fc4d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4fc4d-110">claimType</span><span class="sxs-lookup"><span data-stu-id="4fc4d-110">claimType</span></span>|<span data-ttu-id="4fc4d-111">Универсальный код ресурса (URI), определяющий тип утверждения, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fc4d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4fc4d-112">Child Elements</span></span>  
 <span data-ttu-id="4fc4d-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4fc4d-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4fc4d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4fc4d-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="4fc4d-115">Element</span></span>|<span data-ttu-id="4fc4d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4fc4d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="4fc4d-117">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="4fc4d-118">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="4fc4d-119">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="4fc4d-120">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="4fc4d-121">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4fc4d-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4fc4d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4fc4d-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
