---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 2ef674dc8601bc9afaf6b547265988bb8a99f943
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170172"
---
# \<parameter>

<span data-ttu-id="cdfc5-101">Указывает общий параметр, если объявленный тип является общим типом.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-101">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**  
  
## <a name="syntax"></a><span data-ttu-id="cdfc5-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdfc5-102">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdfc5-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cdfc5-103">Attributes and Elements</span></span>  

 <span data-ttu-id="cdfc5-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdfc5-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cdfc5-105">Attributes</span></span>  
  
|<span data-ttu-id="cdfc5-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cdfc5-106">Attribute</span></span>|<span data-ttu-id="cdfc5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cdfc5-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cdfc5-108">index</span><span class="sxs-lookup"><span data-stu-id="cdfc5-108">index</span></span>|<span data-ttu-id="cdfc5-109">Если объявленный тип является общим типом, указывает общий параметр, который возвращает известный тип.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-109">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="cdfc5-110">тип</span><span class="sxs-lookup"><span data-stu-id="cdfc5-110">type</span></span>|<span data-ttu-id="cdfc5-111">Строка, которая описывает известный тип, используемый для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-111">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="cdfc5-112">Атрибут index</span><span class="sxs-lookup"><span data-stu-id="cdfc5-112">index Attribute</span></span>  
  
|<span data-ttu-id="cdfc5-113">Значение</span><span class="sxs-lookup"><span data-stu-id="cdfc5-113">Value</span></span>|<span data-ttu-id="cdfc5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cdfc5-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cdfc5-115">"0"</span><span class="sxs-lookup"><span data-stu-id="cdfc5-115">"0"</span></span>|<span data-ttu-id="cdfc5-116">Первый параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-116">The first parameter in the generic type.</span></span> <span data-ttu-id="cdfc5-117">Например, у <xref:System.Collections.Generic.List%601> есть только один параметр.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-117">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="cdfc5-118">Если он используется как объявленный тип, индексу присваивается значение 0.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-118">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="cdfc5-119">"1"</span><span class="sxs-lookup"><span data-stu-id="cdfc5-119">"1"</span></span>|<span data-ttu-id="cdfc5-120">Второй параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-120">The second parameter in a generic type.</span></span> <span data-ttu-id="cdfc5-121">Например, у <xref:System.Collections.Generic.Dictionary%602> есть два параметра.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-121">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="cdfc5-122">Если известный тип возвращается вторым параметром, атрибуту index присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-122">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cdfc5-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cdfc5-123">Child Elements</span></span>  

 <span data-ttu-id="cdfc5-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cdfc5-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cdfc5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="cdfc5-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="cdfc5-126">Element</span></span>|<span data-ttu-id="cdfc5-127">Описание</span><span class="sxs-lookup"><span data-stu-id="cdfc5-127">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="cdfc5-128">Указывает известный тип, который может возвращаться полем или свойством объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-128">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdfc5-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="cdfc5-129">Remarks</span></span>  

 <span data-ttu-id="cdfc5-130">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="cdfc5-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="cdfc5-131">[\<dataContractSerializer>](datacontractserializer-element.md)Пример использования этого элемента см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="cdfc5-132">У данного элемента конфигурации не может одновременно быть оба атрибута.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-132">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="cdfc5-133">Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="cdfc5-133">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfc5-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cdfc5-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="cdfc5-135">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="cdfc5-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
