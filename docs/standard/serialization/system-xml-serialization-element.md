---
title: Элемент <system.xml.serialization>
description: В статье описан <system.xml.serialization> — элемент верхнего уровня для управления сериализацией XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 1e66220004d561f937d03c506e6f30db4ccc635b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380115"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="8139a-103">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="8139a-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="8139a-104">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="8139a-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="8139a-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="8139a-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="8139a-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8139a-106">\<configuration></span></span>\
<span data-ttu-id="8139a-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="8139a-107">\<system.xml.serialization></span></span>

## <a name="syntax"></a><span data-ttu-id="8139a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8139a-108">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8139a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8139a-109">Attributes and Elements</span></span>

<span data-ttu-id="8139a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8139a-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8139a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8139a-111">Attributes</span></span>

<span data-ttu-id="8139a-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8139a-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8139a-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8139a-113">Child Elements</span></span>

|<span data-ttu-id="8139a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8139a-114">Element</span></span>|<span data-ttu-id="8139a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8139a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8139a-116">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="8139a-116">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="8139a-117">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="8139a-117">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="8139a-118">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="8139a-118">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="8139a-119">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8139a-119">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8139a-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8139a-120">Parent Elements</span></span>

|<span data-ttu-id="8139a-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="8139a-121">Element</span></span>|<span data-ttu-id="8139a-122">Описание</span><span class="sxs-lookup"><span data-stu-id="8139a-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8139a-123">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="8139a-123">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="8139a-124">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8139a-124">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="8139a-125">Пример</span><span class="sxs-lookup"><span data-stu-id="8139a-125">Example</span></span>

<span data-ttu-id="8139a-126">В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8139a-126">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a><span data-ttu-id="8139a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8139a-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="8139a-128">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8139a-128">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="8139a-129">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="8139a-129">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="8139a-130">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="8139a-130">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="8139a-131">Элемент \<add> для элемента \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="8139a-131">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
