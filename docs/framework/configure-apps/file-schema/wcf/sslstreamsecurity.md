---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: aa6bc7f5a94afc8a190d3d9d2d71ea8b38d8c25b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153577"
---
# \<sslStreamSecurity>

<span data-ttu-id="16dd4-101">Представляет пользовательский элемент привязки, который поддерживает безопасность канала с помощью потока SSL.</span><span class="sxs-lookup"><span data-stu-id="16dd4-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="16dd4-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16dd4-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16dd4-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="16dd4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="16dd4-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="16dd4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16dd4-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="16dd4-105">Attributes</span></span>  
  
|<span data-ttu-id="16dd4-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="16dd4-106">Attribute</span></span>|<span data-ttu-id="16dd4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="16dd4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16dd4-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="16dd4-108">requireClientCertificate</span></span>|<span data-ttu-id="16dd4-109">Логическое значение, указывающее, требуется ли для этой привязки сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="16dd4-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="16dd4-110">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="16dd4-110">The default is `false`.</span></span>|  
|<span data-ttu-id="16dd4-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="16dd4-111">sslProtocols</span></span>|<span data-ttu-id="16dd4-112">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="16dd4-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="16dd4-113">Значение по умолчанию — Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="16dd4-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16dd4-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="16dd4-114">Child Elements</span></span>  

 <span data-ttu-id="16dd4-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="16dd4-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16dd4-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="16dd4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="16dd4-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="16dd4-117">Element</span></span>|<span data-ttu-id="16dd4-118">Описание</span><span class="sxs-lookup"><span data-stu-id="16dd4-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="16dd4-119">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="16dd4-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16dd4-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="16dd4-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="16dd4-121">Привязки</span><span class="sxs-lookup"><span data-stu-id="16dd4-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="16dd4-122">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="16dd4-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="16dd4-123">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="16dd4-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
