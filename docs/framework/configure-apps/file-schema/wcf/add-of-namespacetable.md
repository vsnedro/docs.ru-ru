---
title: <add> из <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7d055d4933f1ad625d6842f91a140f668c05c64e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205000"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="cf70d-102">\<add> из \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="cf70d-102">\<add> of \<namespaceTable></span></span>

<span data-ttu-id="cf70d-103">Представляет элемент конфигурации, содержащий пространство имен, используемое в качестве префикса сопоставления, которое затем можно использовать в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="cf70d-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="cf70d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf70d-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf70d-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cf70d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="cf70d-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cf70d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf70d-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cf70d-107">Attributes</span></span>  
  
|<span data-ttu-id="cf70d-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cf70d-108">Attribute</span></span>|<span data-ttu-id="cf70d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cf70d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf70d-110">namespace</span><span class="sxs-lookup"><span data-stu-id="cf70d-110">namespace</span></span>|<span data-ttu-id="cf70d-111">Строка, содержащая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="cf70d-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="cf70d-112">prefix</span><span class="sxs-lookup"><span data-stu-id="cf70d-112">prefix</span></span>|<span data-ttu-id="cf70d-113">Строка, содержащая префикс этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cf70d-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf70d-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cf70d-114">Child Elements</span></span>  

 <span data-ttu-id="cf70d-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cf70d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf70d-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cf70d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cf70d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf70d-117">Element</span></span>|<span data-ttu-id="cf70d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="cf70d-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="cf70d-119">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="cf70d-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf70d-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cf70d-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
