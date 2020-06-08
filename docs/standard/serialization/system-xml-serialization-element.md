---
title: Элемент <system.xml.serialization>
description: В статье описан <system.xml.serialization> — элемент верхнего уровня для управления сериализацией XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f69e80592e9321de64421b977a63b83d8be2ad9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289490"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="245ef-103">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="245ef-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="245ef-104">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="245ef-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="245ef-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="245ef-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a><span data-ttu-id="245ef-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="245ef-106">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="245ef-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="245ef-107">Attributes and Elements</span></span>

<span data-ttu-id="245ef-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="245ef-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="245ef-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="245ef-109">Attributes</span></span>

<span data-ttu-id="245ef-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="245ef-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="245ef-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="245ef-111">Child Elements</span></span>

|<span data-ttu-id="245ef-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="245ef-112">Element</span></span>|<span data-ttu-id="245ef-113">Описание</span><span class="sxs-lookup"><span data-stu-id="245ef-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="245ef-114">\<dateTimeSerialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="245ef-114">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)|<span data-ttu-id="245ef-115">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="245ef-115">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="245ef-116">\<schemaImporterExtensions> Элемент</span><span class="sxs-lookup"><span data-stu-id="245ef-116">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)|<span data-ttu-id="245ef-117">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="245ef-117">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="245ef-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="245ef-118">Parent Elements</span></span>

|<span data-ttu-id="245ef-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="245ef-119">Element</span></span>|<span data-ttu-id="245ef-120">Описание</span><span class="sxs-lookup"><span data-stu-id="245ef-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="245ef-121">\<configuration> Элемент</span><span class="sxs-lookup"><span data-stu-id="245ef-121">\<configuration> Element</span></span>](../../framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="245ef-122">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="245ef-122">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="245ef-123">Пример</span><span class="sxs-lookup"><span data-stu-id="245ef-123">Example</span></span>

<span data-ttu-id="245ef-124">В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="245ef-124">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="245ef-125">См. также</span><span class="sxs-lookup"><span data-stu-id="245ef-125">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="245ef-126">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="245ef-126">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="245ef-127">\<dateTimeSerialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="245ef-127">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="245ef-128">\<schemaImporterExtensions> Элемент</span><span class="sxs-lookup"><span data-stu-id="245ef-128">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="245ef-129">Элемент \<add> для \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="245ef-129">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
