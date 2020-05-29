---
title: Элемент <dateTimeSerialization>
description: В этой статье описывается элемент <dateTimeSerialization>, который определяет режим сериализации объектов DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 652a88e25f59cd905e47ef71351e47e67f375286
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375827"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="ad1cb-103">\<Элемент dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="ad1cb-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="ad1cb-104">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="ad1cb-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ad1cb-105">\<configuration></span></span>  
<span data-ttu-id="ad1cb-106">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="ad1cb-106">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad1cb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad1cb-107">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad1cb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ad1cb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ad1cb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad1cb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad1cb-110">Attributes</span></span>  
  
|<span data-ttu-id="ad1cb-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad1cb-111">Attributes</span></span>|<span data-ttu-id="ad1cb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ad1cb-112">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="ad1cb-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-113">Optional.</span></span> <span data-ttu-id="ad1cb-114">Задает режим сериализации.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-114">Specifies the serialization mode.</span></span> <span data-ttu-id="ad1cb-115">Задайте одно из значений <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-115">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="ad1cb-116">Значение по умолчанию: **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-116">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad1cb-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad1cb-117">Child Elements</span></span>  
 <span data-ttu-id="ad1cb-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad1cb-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad1cb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ad1cb-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad1cb-120">Element</span></span>|<span data-ttu-id="ad1cb-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ad1cb-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad1cb-122">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="ad1cb-122">system.xml.serialization</span></span>|<span data-ttu-id="ad1cb-123">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-123">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad1cb-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad1cb-124">Remarks</span></span>  
 <span data-ttu-id="ad1cb-125">На платформе .NET Framework версий 1.0, 1.1 и 2.0 и более поздних при присвоении этому свойству значения **Local** объекты <xref:System.DateTime> всегда форматируются как местное время.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-125">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="ad1cb-126">Это значит, что в сериализованные данные всегда включается информация о местном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-126">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="ad1cb-127">Присвоение этому свойству значения **Local** обеспечивает совместимость с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-127">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ad1cb-128">На платформе .NET Framework версии 2.0 и более поздних, в которых для этого свойства задано значение **Roundtrip**, объекты <xref:System.DateTime> анализируются с целью выяснить, указан ли в них местный часовой пояс, время UTC или часовой пояс не указан.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-128">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="ad1cb-129">После этого объекты <xref:System.DateTime> сериализуются способом, обеспечивающим сохранение этой информации.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-129">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="ad1cb-130">Это является поведением по умолчанию, рекомендуемым для всех новых приложений, не взаимодействующих со старыми версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad1cb-130">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad1cb-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ad1cb-131">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="ad1cb-132">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ad1cb-132">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ad1cb-133">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ad1cb-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="ad1cb-134">Элемент \<add> для элемента \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ad1cb-134">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="ad1cb-135">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="ad1cb-135">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
