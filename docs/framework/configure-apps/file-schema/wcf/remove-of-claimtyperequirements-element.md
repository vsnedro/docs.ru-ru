---
title: <remove> элемента <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 773f37156969f64f02711e6a60764aeb7e50a840
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181327"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="f3d92-102">\<remove> элемента \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="f3d92-102">\<remove> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="f3d92-103">Указывает типы утверждений в федеративных учетных данных, которые должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="f3d92-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="f3d92-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3d92-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3d92-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3d92-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f3d92-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3d92-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3d92-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3d92-107">Attributes</span></span>  
  
|<span data-ttu-id="f3d92-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3d92-108">Attribute</span></span>|<span data-ttu-id="f3d92-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f3d92-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3d92-110">claimType</span><span class="sxs-lookup"><span data-stu-id="f3d92-110">claimType</span></span>|<span data-ttu-id="f3d92-111">Универсальный код ресурса (URI), определяющий тип утверждения, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="f3d92-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3d92-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3d92-112">Child Elements</span></span>  

 <span data-ttu-id="f3d92-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f3d92-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3d92-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3d92-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f3d92-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3d92-115">Element</span></span>|<span data-ttu-id="f3d92-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f3d92-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="f3d92-117">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="f3d92-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="f3d92-118">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="f3d92-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="f3d92-119">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="f3d92-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="f3d92-120">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="f3d92-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="f3d92-121">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f3d92-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3d92-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f3d92-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
