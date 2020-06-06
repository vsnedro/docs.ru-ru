---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: c45a4e67d0a2d98c0e9c1a91e07f25b81370244c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398052"
---
# \<declaredTypes>
<span data-ttu-id="d1f76-101">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="d1f76-101">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="d1f76-102">Дополнительные сведения о контрактах данных и известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="d1f76-102">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<declaredTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="d1f76-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1f76-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1f76-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d1f76-104">Attributes and Elements</span></span>  
 <span data-ttu-id="d1f76-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d1f76-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1f76-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1f76-106">Attributes</span></span>  
 <span data-ttu-id="d1f76-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d1f76-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d1f76-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d1f76-108">Child Elements</span></span>  
  
|<span data-ttu-id="d1f76-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1f76-109">Element</span></span>|<span data-ttu-id="d1f76-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d1f76-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="d1f76-111">Добавляет типы, для которых необходимы известные типы.</span><span class="sxs-lookup"><span data-stu-id="d1f76-111">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1f76-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d1f76-112">Parent Elements</span></span>  
  
|<span data-ttu-id="d1f76-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1f76-113">Element</span></span>|<span data-ttu-id="d1f76-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d1f76-114">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="d1f76-115">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d1f76-115">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1f76-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1f76-116">Remarks</span></span>  
 <span data-ttu-id="d1f76-117">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="d1f76-117">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1f76-118">Пример</span><span class="sxs-lookup"><span data-stu-id="d1f76-118">Example</span></span>  
 <span data-ttu-id="d1f76-119">В следующем коде XML показаны объявленные типы и известные типы, добавленные в `DataContractSerializer` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1f76-119">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="d1f76-120">В этом примере показаны три добавляемых типа.</span><span class="sxs-lookup"><span data-stu-id="d1f76-120">The example shows three types being added.</span></span> <span data-ttu-id="d1f76-121">Первый тип - это пользовательский тип с именем «Orders», использующий известный тип с именем «Item».</span><span class="sxs-lookup"><span data-stu-id="d1f76-121">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="d1f76-122">Второй объявленный тип - это <xref:System.Collections.Generic.List%601>, использующий `Item` в качестве известного типа.</span><span class="sxs-lookup"><span data-stu-id="d1f76-122">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="d1f76-123">Наконец, третий объявленный тип - это <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="d1f76-123">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="d1f76-124">Тип класса <xref:System.Collections.Generic.Dictionary%602> является универсальным типом с двумя параметрами типов.</span><span class="sxs-lookup"><span data-stu-id="d1f76-124">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="d1f76-125">Первый представляет ключ, а второй представляет значение.</span><span class="sxs-lookup"><span data-stu-id="d1f76-125">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="d1f76-126">В следующем примере параметр второго типа <xref:System.Collections.Generic.List%601> (значение) добавляется к списку известных типов.</span><span class="sxs-lookup"><span data-stu-id="d1f76-126">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="d1f76-127">Чтобы задать параметр типа для использования в известном типе, необходимо использовать атрибут `index`.</span><span class="sxs-lookup"><span data-stu-id="d1f76-127">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="d1f76-128">В данном примере тип значения указан атрибутом индекса, для которого задано значение 1 (коллекция начинается с нуля).</span><span class="sxs-lookup"><span data-stu-id="d1f76-128">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="d1f76-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d1f76-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="d1f76-130">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="d1f76-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<add>](add-of-declaredtypes-element.md)
