---
title: Элемент <dateTimeSerialization>
description: В этой статье описывается элемент <dateTimeSerialization>, который определяет режим сериализации объектов DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: a2684ab72c1fb109d711e333e01836d3399caf86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289646"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="71a20-103">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="71a20-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="71a20-104">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="71a20-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="71a20-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71a20-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71a20-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="71a20-106">Attributes and Elements</span></span>  
 <span data-ttu-id="71a20-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="71a20-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71a20-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="71a20-108">Attributes</span></span>  
  
|<span data-ttu-id="71a20-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="71a20-109">Attributes</span></span>|<span data-ttu-id="71a20-110">Описание</span><span class="sxs-lookup"><span data-stu-id="71a20-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="71a20-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="71a20-111">Optional.</span></span> <span data-ttu-id="71a20-112">Задает режим сериализации.</span><span class="sxs-lookup"><span data-stu-id="71a20-112">Specifies the serialization mode.</span></span> <span data-ttu-id="71a20-113">Задайте одно из значений <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="71a20-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="71a20-114">Значение по умолчанию: **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="71a20-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71a20-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="71a20-115">Child Elements</span></span>  
 <span data-ttu-id="71a20-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="71a20-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71a20-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="71a20-117">Parent Elements</span></span>  
  
|<span data-ttu-id="71a20-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="71a20-118">Element</span></span>|<span data-ttu-id="71a20-119">Описание</span><span class="sxs-lookup"><span data-stu-id="71a20-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71a20-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="71a20-120">system.xml.serialization</span></span>|<span data-ttu-id="71a20-121">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="71a20-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71a20-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="71a20-122">Remarks</span></span>  
 <span data-ttu-id="71a20-123">На платформе .NET Framework версий 1.0, 1.1 и 2.0 и более поздних при присвоении этому свойству значения **Local** объекты <xref:System.DateTime> всегда форматируются как местное время.</span><span class="sxs-lookup"><span data-stu-id="71a20-123">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="71a20-124">Это значит, что в сериализованные данные всегда включается информация о местном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="71a20-124">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="71a20-125">Присвоение этому свойству значения **Local** обеспечивает совместимость с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="71a20-125">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="71a20-126">На платформе .NET Framework версии 2.0 и более поздних, в которых для этого свойства задано значение **Roundtrip**, объекты <xref:System.DateTime> анализируются с целью выяснить, указан ли в них местный часовой пояс, время UTC или часовой пояс не указан.</span><span class="sxs-lookup"><span data-stu-id="71a20-126">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="71a20-127">После этого объекты <xref:System.DateTime> сериализуются способом, обеспечивающим сохранение этой информации.</span><span class="sxs-lookup"><span data-stu-id="71a20-127">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="71a20-128">Это является поведением по умолчанию, рекомендуемым для всех новых приложений, не взаимодействующих со старыми версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="71a20-128">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a20-129">См. также</span><span class="sxs-lookup"><span data-stu-id="71a20-129">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="71a20-130">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="71a20-130">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="71a20-131">\<schemaImporterExtensions> Элемент</span><span class="sxs-lookup"><span data-stu-id="71a20-131">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="71a20-132">Элемент \<add> для \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="71a20-132">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="71a20-133">\<system.xml.serialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="71a20-133">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
