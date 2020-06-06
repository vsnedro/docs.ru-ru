---
title: <add> из <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850398"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="40f24-102">\<add> из \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="40f24-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="40f24-103">Представляет элемент конфигурации, содержащий пространство имен, используемое в качестве префикса сопоставления, которое затем можно использовать в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="40f24-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="40f24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40f24-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40f24-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="40f24-105">Attributes and Elements</span></span>  
 <span data-ttu-id="40f24-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="40f24-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40f24-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="40f24-107">Attributes</span></span>  
  
|<span data-ttu-id="40f24-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="40f24-108">Attribute</span></span>|<span data-ttu-id="40f24-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="40f24-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40f24-110">namespace</span><span class="sxs-lookup"><span data-stu-id="40f24-110">namespace</span></span>|<span data-ttu-id="40f24-111">Строка, содержащая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="40f24-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="40f24-112">prefix</span><span class="sxs-lookup"><span data-stu-id="40f24-112">prefix</span></span>|<span data-ttu-id="40f24-113">Строка, содержащая префикс этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="40f24-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40f24-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="40f24-114">Child Elements</span></span>  
 <span data-ttu-id="40f24-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="40f24-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40f24-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="40f24-116">Parent Elements</span></span>  
  
|<span data-ttu-id="40f24-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="40f24-117">Element</span></span>|<span data-ttu-id="40f24-118">Описание</span><span class="sxs-lookup"><span data-stu-id="40f24-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="40f24-119">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="40f24-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40f24-120">См. также</span><span class="sxs-lookup"><span data-stu-id="40f24-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
