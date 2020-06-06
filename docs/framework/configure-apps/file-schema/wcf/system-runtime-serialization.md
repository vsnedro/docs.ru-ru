---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152974"
---
# \<system.runtime.serialization>
<span data-ttu-id="01964-102">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="01964-102">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="01964-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01964-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01964-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="01964-104">Attributes and Elements</span></span>  
 <span data-ttu-id="01964-105">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="01964-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01964-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="01964-106">Attributes</span></span>  
 <span data-ttu-id="01964-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="01964-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="01964-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="01964-108">Child Elements</span></span>  
  
|<span data-ttu-id="01964-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="01964-109">Element</span></span>|<span data-ttu-id="01964-110">Описание</span><span class="sxs-lookup"><span data-stu-id="01964-110">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="01964-111">Включает добавление известных типов при десериализации.</span><span class="sxs-lookup"><span data-stu-id="01964-111">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01964-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="01964-112">Parent Elements</span></span>  
  
|<span data-ttu-id="01964-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="01964-113">Element</span></span>|<span data-ttu-id="01964-114">Описание</span><span class="sxs-lookup"><span data-stu-id="01964-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01964-115">\<configuration>Дерев</span><span class="sxs-lookup"><span data-stu-id="01964-115">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="01964-116">Элемент конфигурации верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="01964-116">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01964-117">См. также</span><span class="sxs-lookup"><span data-stu-id="01964-117">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="01964-118">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="01964-118">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="01964-119">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="01964-119">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
