---
title: <clear> элемента <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: aa94a012da11bcec6fb5fe270ad9f3574f88e6d7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172909"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="85c80-102">\<clear> элемента \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="85c80-102">\<clear> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="85c80-103">Указывает, что все типы утверждений в федеративных учетных данных должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="85c80-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="85c80-104">Это обеспечивает запуск пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="85c80-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="85c80-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85c80-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85c80-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="85c80-106">Attributes and Elements</span></span>  

 <span data-ttu-id="85c80-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="85c80-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85c80-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="85c80-108">Attributes</span></span>  

 <span data-ttu-id="85c80-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="85c80-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="85c80-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="85c80-110">Child Elements</span></span>  

 <span data-ttu-id="85c80-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="85c80-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85c80-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="85c80-112">Parent Elements</span></span>  
  
|<span data-ttu-id="85c80-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="85c80-113">Element</span></span>|<span data-ttu-id="85c80-114">Описание</span><span class="sxs-lookup"><span data-stu-id="85c80-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="85c80-115">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="85c80-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="85c80-116">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="85c80-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="85c80-117">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="85c80-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="85c80-118">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="85c80-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="85c80-119">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="85c80-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85c80-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="85c80-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
