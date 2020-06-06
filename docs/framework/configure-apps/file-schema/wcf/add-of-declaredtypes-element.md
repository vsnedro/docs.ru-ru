---
title: <add> элемента <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400659"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="b019c-102">\<add> элемента \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="b019c-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="b019c-103">Добавляет тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="b019c-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="b019c-104">В каждый объявленный тип включены известные типы, которые будут возвращены как поле или свойство объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="b019c-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b019c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b019c-105">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b019c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b019c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b019c-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b019c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b019c-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b019c-108">Attributes</span></span>  
  
|<span data-ttu-id="b019c-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b019c-109">Attribute</span></span>|<span data-ttu-id="b019c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b019c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b019c-111">type</span><span class="sxs-lookup"><span data-stu-id="b019c-111">type</span></span>|<span data-ttu-id="b019c-112">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="b019c-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="b019c-113">Задает имя типа (в том числе пространство имен), имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="b019c-113">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b019c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b019c-114">Child Elements</span></span>  
  
|<span data-ttu-id="b019c-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="b019c-115">Element</span></span>|<span data-ttu-id="b019c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b019c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="b019c-117">Задает известный тип для добавляемого объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="b019c-117">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="b019c-118">Если объявленный тип является универсальным типом, необходимо также добавить элемент параметра к элементу `<knownType>`, чтобы указать, какой универсальный параметр будет использоваться для возвращения известного типа.</span><span class="sxs-lookup"><span data-stu-id="b019c-118">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b019c-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b019c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b019c-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="b019c-120">Element</span></span>|<span data-ttu-id="b019c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b019c-121">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="b019c-122">Содержит типы, для которых необходимы известные типы во время десериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b019c-122">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b019c-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="b019c-123">Remarks</span></span>  
 <span data-ttu-id="b019c-124">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="b019c-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b019c-125">[\<dataContractSerializer>](datacontractserializer-element.md)Пример использования этого элемента см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="b019c-125">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b019c-126">При добавлении типа <xref:System.Object> как `<declaredType>` возникает <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="b019c-126">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="b019c-127">Это обусловлено тем, что тип <xref:System.Object> нельзя использовать как объявленный тип в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b019c-127">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b019c-128">Пример</span><span class="sxs-lookup"><span data-stu-id="b019c-128">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="b019c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="b019c-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="b019c-130">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="b019c-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="b019c-131">\<add>окна\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="b019c-131">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
