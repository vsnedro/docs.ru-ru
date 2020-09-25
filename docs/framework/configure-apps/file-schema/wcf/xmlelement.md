---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 0ab7fbd64cc92e940617f5334eeb16fcb3a50c4a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181236"
---
# \<xmlElement>

<span data-ttu-id="81a04-101">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="81a04-101">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="81a04-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81a04-102">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81a04-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="81a04-103">Attributes and Elements</span></span>  

 <span data-ttu-id="81a04-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="81a04-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81a04-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="81a04-105">Attributes</span></span>  
  
|<span data-ttu-id="81a04-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="81a04-106">Attribute</span></span>|<span data-ttu-id="81a04-107">Описание</span><span class="sxs-lookup"><span data-stu-id="81a04-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81a04-108">xmlElement</span><span class="sxs-lookup"><span data-stu-id="81a04-108">xmlElement</span></span>|<span data-ttu-id="81a04-109">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="81a04-109">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81a04-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="81a04-110">Child Elements</span></span>  

 <span data-ttu-id="81a04-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="81a04-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81a04-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="81a04-112">Parent Elements</span></span>  
  
|<span data-ttu-id="81a04-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="81a04-113">Element</span></span>|<span data-ttu-id="81a04-114">Описание</span><span class="sxs-lookup"><span data-stu-id="81a04-114">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="81a04-115">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="81a04-115">A collection of token request parameters.</span></span> <span data-ttu-id="81a04-116">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="81a04-116">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81a04-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81a04-117">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="81a04-118">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="81a04-118">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="81a04-119">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="81a04-119">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="81a04-120">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="81a04-120">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="81a04-121">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="81a04-121">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="81a04-122">Привязки</span><span class="sxs-lookup"><span data-stu-id="81a04-122">Bindings</span></span>](../../../wcf/bindings.md)
