---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400454"
---
# \<dataContractSerializer>
<span data-ttu-id="f5fde-101">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f5fde-101">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="f5fde-102">Этот элемент присутствует в двух разных иерархиях.</span><span class="sxs-lookup"><span data-stu-id="f5fde-102">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="f5fde-103">Одна из них указана в следующем разделе «Иерархия схемы», а другая - в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="f5fde-103">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="f5fde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5fde-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5fde-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f5fde-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f5fde-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f5fde-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5fde-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f5fde-107">Attributes</span></span>  
  
|<span data-ttu-id="f5fde-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5fde-108">Element</span></span>|<span data-ttu-id="f5fde-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f5fde-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5fde-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="f5fde-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="f5fde-111">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="f5fde-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="f5fde-112">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="f5fde-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="f5fde-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="f5fde-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="f5fde-114">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="f5fde-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="f5fde-115">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="f5fde-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5fde-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f5fde-116">Child Elements</span></span>  
 <span data-ttu-id="f5fde-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f5fde-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5fde-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f5fde-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f5fde-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5fde-119">Element</span></span>|<span data-ttu-id="f5fde-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f5fde-120">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="f5fde-121">Коллекция параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="f5fde-121">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="f5fde-122">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f5fde-122">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5fde-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5fde-123">Remarks</span></span>  
 <span data-ttu-id="f5fde-124">Как указано в статье Введение в этот раздел, это вторая иерархия, в которой \<X509Extension> происходит элемент.</span><span class="sxs-lookup"><span data-stu-id="f5fde-124">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="f5fde-125">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f5fde-125">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5fde-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f5fde-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="f5fde-127">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="f5fde-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="f5fde-128">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="f5fde-128">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
