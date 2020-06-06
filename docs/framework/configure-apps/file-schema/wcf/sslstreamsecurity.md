---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738595"
---
# \<sslStreamSecurity>
<span data-ttu-id="0ea31-101">Представляет пользовательский элемент привязки, который поддерживает безопасность канала с помощью потока SSL.</span><span class="sxs-lookup"><span data-stu-id="0ea31-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="0ea31-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ea31-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ea31-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0ea31-103">Attributes and Elements</span></span>  
 <span data-ttu-id="0ea31-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0ea31-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ea31-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0ea31-105">Attributes</span></span>  
  
|<span data-ttu-id="0ea31-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0ea31-106">Attribute</span></span>|<span data-ttu-id="0ea31-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0ea31-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ea31-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="0ea31-108">requireClientCertificate</span></span>|<span data-ttu-id="0ea31-109">Логическое значение, указывающее, требуется ли для этой привязки сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="0ea31-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="0ea31-110">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="0ea31-110">The default is `false`.</span></span>|  
|<span data-ttu-id="0ea31-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="0ea31-111">sslProtocols</span></span>|<span data-ttu-id="0ea31-112">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0ea31-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="0ea31-113">Значение по умолчанию — Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="0ea31-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ea31-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0ea31-114">Child Elements</span></span>  
 <span data-ttu-id="0ea31-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0ea31-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ea31-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0ea31-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0ea31-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="0ea31-117">Element</span></span>|<span data-ttu-id="0ea31-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0ea31-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0ea31-119">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="0ea31-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ea31-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0ea31-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="0ea31-121">Привязки</span><span class="sxs-lookup"><span data-stu-id="0ea31-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0ea31-122">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="0ea31-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0ea31-123">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="0ea31-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
