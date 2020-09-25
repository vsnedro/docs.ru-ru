---
title: <dataContractSerializer> <System. Runtime. Serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: a8d379e7a37bca0cdb58836a6afdf814320e2411
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190193"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="89273-102">\<dataContractSerializer> из \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="89273-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>

<span data-ttu-id="89273-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="89273-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="89273-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89273-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89273-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89273-105">Attributes and Elements</span></span>  

 <span data-ttu-id="89273-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="89273-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89273-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89273-107">Attributes</span></span>  
  
|<span data-ttu-id="89273-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="89273-108">Element</span></span>|<span data-ttu-id="89273-109">Описание</span><span class="sxs-lookup"><span data-stu-id="89273-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89273-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="89273-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="89273-111">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="89273-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="89273-112">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="89273-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="89273-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="89273-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="89273-114">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="89273-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="89273-115">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="89273-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89273-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89273-116">Child Elements</span></span>  
  
|<span data-ttu-id="89273-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="89273-117">Element</span></span>|<span data-ttu-id="89273-118">Описание</span><span class="sxs-lookup"><span data-stu-id="89273-118">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="89273-119">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="89273-119">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="89273-120">Дополнительные сведения о контрактах данных и известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="89273-120">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89273-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89273-121">Parent Elements</span></span>  
  
|<span data-ttu-id="89273-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="89273-122">Element</span></span>|<span data-ttu-id="89273-123">Описание</span><span class="sxs-lookup"><span data-stu-id="89273-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="89273-124">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="89273-124">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89273-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="89273-125">Remarks</span></span>  

 <span data-ttu-id="89273-126">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer> и [известные типы контракта данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="89273-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89273-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="89273-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="89273-128">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="89273-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
