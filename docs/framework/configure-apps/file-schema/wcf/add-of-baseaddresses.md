---
title: <add> из <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: cd0ef5cc5f0f809bdafa23bd312e7e30fcdccc21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181613"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="23367-102">\<add> из \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="23367-102">\<add> of \<baseAddresses></span></span>

<span data-ttu-id="23367-103">Представляет элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="23367-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="23367-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23367-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="23367-105">Type</span><span class="sxs-lookup"><span data-stu-id="23367-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23367-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="23367-106">Attributes and Elements</span></span>  

 <span data-ttu-id="23367-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="23367-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23367-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="23367-108">Attributes</span></span>  
  
|<span data-ttu-id="23367-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="23367-109">Attribute</span></span>|<span data-ttu-id="23367-110">Описание</span><span class="sxs-lookup"><span data-stu-id="23367-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="23367-111">Строка, которая задает базовый адрес, используемый узлом службы.</span><span class="sxs-lookup"><span data-stu-id="23367-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23367-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="23367-112">Child Elements</span></span>  

 <span data-ttu-id="23367-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="23367-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23367-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="23367-114">Parent Elements</span></span>  
  
|<span data-ttu-id="23367-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="23367-115">Element</span></span>|<span data-ttu-id="23367-116">Описание</span><span class="sxs-lookup"><span data-stu-id="23367-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="23367-117">Коллекция элементов `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="23367-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23367-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="23367-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="23367-119">Размещение</span><span class="sxs-lookup"><span data-stu-id="23367-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
