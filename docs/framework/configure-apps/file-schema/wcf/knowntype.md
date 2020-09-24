---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6bb6a419d863172951d82a67de044cb8cfc30f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183797"
---
# \<knownType>

<span data-ttu-id="ff80d-101">Задает тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="ff80d-101">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="ff80d-102">Элемент задает «известный тип», возвращаемый полем или свойством «объявленного типа».</span><span class="sxs-lookup"><span data-stu-id="ff80d-102">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="ff80d-103">Дополнительные сведения см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="ff80d-103">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="ff80d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff80d-104">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="ff80d-105">Type</span><span class="sxs-lookup"><span data-stu-id="ff80d-105">Type</span></span>  

 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff80d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff80d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ff80d-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ff80d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff80d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff80d-108">Attributes</span></span>  
  
|<span data-ttu-id="ff80d-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ff80d-109">Attribute</span></span>|<span data-ttu-id="ff80d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ff80d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff80d-111">type</span><span class="sxs-lookup"><span data-stu-id="ff80d-111">type</span></span>|<span data-ttu-id="ff80d-112">Задает тип (в том числе пространство имен), имя сборки, версию, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="ff80d-112">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff80d-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff80d-113">Child Elements</span></span>  
  
|<span data-ttu-id="ff80d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff80d-114">Element</span></span>|<span data-ttu-id="ff80d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ff80d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="ff80d-116">Задает индекс параметра в том случае, если объявленный тип является универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="ff80d-116">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff80d-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff80d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ff80d-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff80d-118">Element</span></span>|<span data-ttu-id="ff80d-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ff80d-119">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="ff80d-120">Добавляет объявленный тип в коллекцию объявленных типов.</span><span class="sxs-lookup"><span data-stu-id="ff80d-120">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff80d-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff80d-121">Remarks</span></span>  

 <span data-ttu-id="ff80d-122">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="ff80d-122">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="ff80d-123">[\<dataContractSerializer>](datacontractserializer-element.md)Пример использования этого элемента см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="ff80d-123">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff80d-124">Пример</span><span class="sxs-lookup"><span data-stu-id="ff80d-124">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="ff80d-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff80d-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="ff80d-126">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="ff80d-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
