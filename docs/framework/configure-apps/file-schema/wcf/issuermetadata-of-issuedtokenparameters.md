---
title: <issuerMetadata> из <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 389ac9e96c1462f59bc42b2e20cb511acdefda00
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185669"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="fed2e-102">\<issuerMetadata> из \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="fed2e-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="fed2e-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fed2e-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fed2e-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fed2e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="fed2e-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fed2e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fed2e-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fed2e-106">Attributes</span></span>  
  
|<span data-ttu-id="fed2e-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fed2e-107">Attribute</span></span>|<span data-ttu-id="fed2e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fed2e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fed2e-109">address</span><span class="sxs-lookup"><span data-stu-id="fed2e-109">address</span></span>|<span data-ttu-id="fed2e-110">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="fed2e-110">Required.</span></span> <span data-ttu-id="fed2e-111">Строка, задающая адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fed2e-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="fed2e-112">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="fed2e-112">The address must be an absolute URI.</span></span> <span data-ttu-id="fed2e-113">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="fed2e-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fed2e-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fed2e-114">Child Elements</span></span>  
  
|<span data-ttu-id="fed2e-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="fed2e-115">Element</span></span>|<span data-ttu-id="fed2e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="fed2e-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="fed2e-117">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="fed2e-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="fed2e-118">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="fed2e-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fed2e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fed2e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fed2e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="fed2e-120">Element</span></span>|<span data-ttu-id="fed2e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="fed2e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="fed2e-122">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="fed2e-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fed2e-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fed2e-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fed2e-124">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="fed2e-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fed2e-125">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="fed2e-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fed2e-126">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="fed2e-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="fed2e-127">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="fed2e-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fed2e-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="fed2e-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fed2e-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="fed2e-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fed2e-130">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="fed2e-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="fed2e-131">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="fed2e-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="fed2e-132">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="fed2e-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
