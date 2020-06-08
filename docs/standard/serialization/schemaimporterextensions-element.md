---
title: Элемент <schemaImporterExtensions>
description: Элемент <schemaImporterExtensions> содержит типы, которые XmlSchemaImporter использует для сопоставления типов XSD с типами .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: c46c5cb6e01463723f0f2ce3873fb4a6ec0b4e60
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84278406"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="335b6-103">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="335b6-103">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="335b6-104">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="335b6-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="335b6-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="335b6-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="335b6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="335b6-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="335b6-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="335b6-107">Child Elements</span></span>  
  
|<span data-ttu-id="335b6-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="335b6-108">Element</span></span>|<span data-ttu-id="335b6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="335b6-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="335b6-110">Элемент \<add> для \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="335b6-110">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)|<span data-ttu-id="335b6-111">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> для создания сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="335b6-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="335b6-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="335b6-112">Parent Elements</span></span>  
  
|<span data-ttu-id="335b6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="335b6-113">Element</span></span>|<span data-ttu-id="335b6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="335b6-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="335b6-115">\<system.xml.serialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="335b6-115">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="335b6-116">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="335b6-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="335b6-117">Пример</span><span class="sxs-lookup"><span data-stu-id="335b6-117">Example</span></span>  
 <span data-ttu-id="335b6-118">В следующем примере кода показано, как добавлять типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="335b6-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="335b6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="335b6-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="335b6-120">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="335b6-120">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="335b6-121">\<dateTimeSerialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="335b6-121">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="335b6-122">Элемент \<add> для \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="335b6-122">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="335b6-123">\<system.xml.serialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="335b6-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
