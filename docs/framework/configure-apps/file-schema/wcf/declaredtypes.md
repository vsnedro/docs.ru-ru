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
ms.openlocfilehash: 281d9d7d7e51a837de4f86f85472815956a20319
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153915"
---
# \<declaredTypes>

<span data-ttu-id="c18fb-101">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="c18fb-101">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="c18fb-102">Дополнительные сведения о контрактах данных и известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="c18fb-102">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<declaredTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="c18fb-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c18fb-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c18fb-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c18fb-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c18fb-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c18fb-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c18fb-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c18fb-106">Attributes</span></span>  

 <span data-ttu-id="c18fb-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c18fb-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c18fb-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c18fb-108">Child Elements</span></span>  
  
|<span data-ttu-id="c18fb-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="c18fb-109">Element</span></span>|<span data-ttu-id="c18fb-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c18fb-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="c18fb-111">Добавляет типы, для которых необходимы известные типы.</span><span class="sxs-lookup"><span data-stu-id="c18fb-111">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c18fb-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c18fb-112">Parent Elements</span></span>  
  
|<span data-ttu-id="c18fb-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c18fb-113">Element</span></span>|<span data-ttu-id="c18fb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c18fb-114">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="c18fb-115">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c18fb-115">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c18fb-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="c18fb-116">Remarks</span></span>  

 <span data-ttu-id="c18fb-117">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="c18fb-117">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c18fb-118">Пример</span><span class="sxs-lookup"><span data-stu-id="c18fb-118">Example</span></span>  

 <span data-ttu-id="c18fb-119">В следующем коде XML показаны объявленные типы и известные типы, добавленные в `DataContractSerializer` элемент.</span><span class="sxs-lookup"><span data-stu-id="c18fb-119">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="c18fb-120">В этом примере показаны три добавляемых типа.</span><span class="sxs-lookup"><span data-stu-id="c18fb-120">The example shows three types being added.</span></span> <span data-ttu-id="c18fb-121">Первый тип - это пользовательский тип с именем «Orders», использующий известный тип с именем «Item».</span><span class="sxs-lookup"><span data-stu-id="c18fb-121">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="c18fb-122">Второй объявленный тип - это <xref:System.Collections.Generic.List%601>, использующий `Item` в качестве известного типа.</span><span class="sxs-lookup"><span data-stu-id="c18fb-122">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="c18fb-123">Наконец, третий объявленный тип - это <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="c18fb-123">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="c18fb-124">Тип класса <xref:System.Collections.Generic.Dictionary%602> является универсальным типом с двумя параметрами типов.</span><span class="sxs-lookup"><span data-stu-id="c18fb-124">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="c18fb-125">Первый представляет ключ, а второй представляет значение.</span><span class="sxs-lookup"><span data-stu-id="c18fb-125">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="c18fb-126">В следующем примере параметр второго типа <xref:System.Collections.Generic.List%601> (значение) добавляется к списку известных типов.</span><span class="sxs-lookup"><span data-stu-id="c18fb-126">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="c18fb-127">Чтобы задать параметр типа для использования в известном типе, необходимо использовать атрибут `index`.</span><span class="sxs-lookup"><span data-stu-id="c18fb-127">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="c18fb-128">В данном примере тип значения указан атрибутом индекса, для которого задано значение 1 (коллекция начинается с нуля).</span><span class="sxs-lookup"><span data-stu-id="c18fb-128">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c18fb-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c18fb-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="c18fb-130">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c18fb-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<add>](add-of-declaredtypes-element.md)
