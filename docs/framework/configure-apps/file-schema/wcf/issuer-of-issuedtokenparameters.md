---
title: <issuer> из <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bfe8163d2d6baba1d6e8053f7f6579673d8b4b21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157282"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="005e1-102">\<issuer> из \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="005e1-102">\<issuer> of \<issuedTokenParameters></span></span>

<span data-ttu-id="005e1-103">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="005e1-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="005e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="005e1-104">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="005e1-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="005e1-105">Attributes and Elements</span></span>  

 <span data-ttu-id="005e1-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="005e1-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="005e1-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="005e1-107">Attributes</span></span>  
  
|<span data-ttu-id="005e1-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="005e1-108">Attribute</span></span>|<span data-ttu-id="005e1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="005e1-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="005e1-110">address</span><span class="sxs-lookup"><span data-stu-id="005e1-110">address</span></span>|<span data-ttu-id="005e1-111">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="005e1-111">Required string.</span></span> <span data-ttu-id="005e1-112">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="005e1-112">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="005e1-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="005e1-113">Child Elements</span></span>  
  
|<span data-ttu-id="005e1-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="005e1-114">Element</span></span>|<span data-ttu-id="005e1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="005e1-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="005e1-116">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="005e1-116">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="005e1-117">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="005e1-117">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="005e1-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="005e1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="005e1-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="005e1-119">Element</span></span>|<span data-ttu-id="005e1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="005e1-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="005e1-121">Определяет текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="005e1-121">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="005e1-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="005e1-122">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="005e1-123">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="005e1-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="005e1-124">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="005e1-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="005e1-125">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="005e1-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="005e1-126">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="005e1-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="005e1-127">Привязки</span><span class="sxs-lookup"><span data-stu-id="005e1-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="005e1-128">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="005e1-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="005e1-129">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="005e1-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="005e1-130">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="005e1-130">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="005e1-131">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="005e1-131">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
