---
title: <add> из <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d75142209ad8706d0cad5ce188d9d991a5e881bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850584"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="5012a-102">\<add> из \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="5012a-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="5012a-103">Представляет элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="5012a-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="5012a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5012a-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="5012a-105">Type</span><span class="sxs-lookup"><span data-stu-id="5012a-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5012a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5012a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5012a-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5012a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5012a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5012a-108">Attributes</span></span>  
  
|<span data-ttu-id="5012a-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5012a-109">Attribute</span></span>|<span data-ttu-id="5012a-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="5012a-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="5012a-111">Строка, которая задает базовый адрес, используемый узлом службы.</span><span class="sxs-lookup"><span data-stu-id="5012a-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5012a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5012a-112">Child Elements</span></span>  
 <span data-ttu-id="5012a-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5012a-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5012a-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5012a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="5012a-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="5012a-115">Element</span></span>|<span data-ttu-id="5012a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5012a-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="5012a-117">Коллекция элементов `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="5012a-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5012a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5012a-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="5012a-119">Размещение</span><span class="sxs-lookup"><span data-stu-id="5012a-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
