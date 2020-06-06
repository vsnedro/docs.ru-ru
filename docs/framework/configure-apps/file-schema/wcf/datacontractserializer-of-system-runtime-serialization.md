---
title: <dataContractSerializer><System. Runtime. Serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398083"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="b5205-102">\<dataContractSerializer> из \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="b5205-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="b5205-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b5205-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="b5205-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5205-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5205-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b5205-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b5205-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b5205-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5205-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b5205-107">Attributes</span></span>  
  
|<span data-ttu-id="b5205-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5205-108">Element</span></span>|<span data-ttu-id="b5205-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b5205-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5205-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="b5205-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="b5205-111">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="b5205-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="b5205-112">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="b5205-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="b5205-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="b5205-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="b5205-114">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="b5205-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="b5205-115">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="b5205-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5205-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b5205-116">Child Elements</span></span>  
  
|<span data-ttu-id="b5205-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5205-117">Element</span></span>|<span data-ttu-id="b5205-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b5205-118">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="b5205-119">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="b5205-119">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="b5205-120">Дополнительные сведения о контрактах данных и известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="b5205-120">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5205-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b5205-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b5205-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5205-122">Element</span></span>|<span data-ttu-id="b5205-123">Описание</span><span class="sxs-lookup"><span data-stu-id="b5205-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="b5205-124">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b5205-124">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5205-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5205-125">Remarks</span></span>  
 <span data-ttu-id="b5205-126">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer> и [известные типы контракта данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="b5205-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5205-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b5205-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="b5205-128">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="b5205-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
