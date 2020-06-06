---
title: <issuerMetadata> из <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400344"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="a595a-102">\<issuerMetadata> из \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="a595a-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="a595a-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a595a-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a595a-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a595a-104">Attributes and Elements</span></span>  
 <span data-ttu-id="a595a-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a595a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a595a-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a595a-106">Attributes</span></span>  
  
|<span data-ttu-id="a595a-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a595a-107">Attribute</span></span>|<span data-ttu-id="a595a-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="a595a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a595a-109">address</span><span class="sxs-lookup"><span data-stu-id="a595a-109">address</span></span>|<span data-ttu-id="a595a-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a595a-110">Required.</span></span> <span data-ttu-id="a595a-111">Строка, задающая адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a595a-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="a595a-112">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="a595a-112">The address must be an absolute URI.</span></span> <span data-ttu-id="a595a-113">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="a595a-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a595a-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a595a-114">Child Elements</span></span>  
  
|<span data-ttu-id="a595a-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="a595a-115">Element</span></span>|<span data-ttu-id="a595a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a595a-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="a595a-117">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="a595a-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="a595a-118">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a595a-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a595a-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a595a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a595a-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="a595a-120">Element</span></span>|<span data-ttu-id="a595a-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a595a-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="a595a-122">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="a595a-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a595a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a595a-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a595a-124">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="a595a-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a595a-125">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="a595a-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a595a-126">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="a595a-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a595a-127">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="a595a-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a595a-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="a595a-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a595a-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="a595a-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a595a-130">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="a595a-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="a595a-131">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a595a-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="a595a-132">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="a595a-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
