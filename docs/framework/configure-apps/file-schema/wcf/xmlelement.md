---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398987"
---
# \<xmlElement>
<span data-ttu-id="107cd-101">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="107cd-101">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="107cd-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="107cd-102">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="107cd-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="107cd-103">Attributes and Elements</span></span>  
 <span data-ttu-id="107cd-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="107cd-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="107cd-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="107cd-105">Attributes</span></span>  
  
|<span data-ttu-id="107cd-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="107cd-106">Attribute</span></span>|<span data-ttu-id="107cd-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="107cd-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="107cd-108">xmlElement</span><span class="sxs-lookup"><span data-stu-id="107cd-108">xmlElement</span></span>|<span data-ttu-id="107cd-109">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="107cd-109">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="107cd-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="107cd-110">Child Elements</span></span>  
 <span data-ttu-id="107cd-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="107cd-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="107cd-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="107cd-112">Parent Elements</span></span>  
  
|<span data-ttu-id="107cd-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="107cd-113">Element</span></span>|<span data-ttu-id="107cd-114">Описание</span><span class="sxs-lookup"><span data-stu-id="107cd-114">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="107cd-115">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="107cd-115">A collection of token request parameters.</span></span> <span data-ttu-id="107cd-116">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="107cd-116">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="107cd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="107cd-117">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="107cd-118">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="107cd-118">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="107cd-119">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="107cd-119">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="107cd-120">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="107cd-120">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="107cd-121">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="107cd-121">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="107cd-122">Привязки</span><span class="sxs-lookup"><span data-stu-id="107cd-122">Bindings</span></span>](../../../wcf/bindings.md)
