---
title: Элемент <add> для <schemaImporterExtensions>
description: Элемент <add> добавляет типы, используемые классом XmlSchemaImporter для сопоставления типов XSD с типами .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 401d1ba9cc2f97e93d7851f96f73b552e6ed6356
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378477"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="1420b-103">Элемент \<add> для элемента \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="1420b-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="1420b-104">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter>, для сопоставления типов XSD с типами платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1420b-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="1420b-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="1420b-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="1420b-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1420b-106">\<configuration></span></span>  
<span data-ttu-id="1420b-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="1420b-107">\<system.xml.serialization></span></span>  
<span data-ttu-id="1420b-108">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="1420b-108">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="1420b-109">\<add></span><span class="sxs-lookup"><span data-stu-id="1420b-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1420b-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1420b-110">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1420b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1420b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1420b-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1420b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1420b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1420b-113">Attributes</span></span>  
  
|<span data-ttu-id="1420b-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1420b-114">Attribute</span></span>|<span data-ttu-id="1420b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1420b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1420b-116">**name**</span><span class="sxs-lookup"><span data-stu-id="1420b-116">**name**</span></span>|<span data-ttu-id="1420b-117">Простое имя, используемое для поиска экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1420b-117">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="1420b-118">**type**</span><span class="sxs-lookup"><span data-stu-id="1420b-118">**type**</span></span>|<span data-ttu-id="1420b-119">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="1420b-119">Required.</span></span> <span data-ttu-id="1420b-120">Задает добавляемый класс расширения схемы.</span><span class="sxs-lookup"><span data-stu-id="1420b-120">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="1420b-121">Значение атрибута **type** должно располагаться на одной строке и содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="1420b-121">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="1420b-122">Когда сборка помещается в глобальный кэш сборок (GAC), она должна также содержать версию, язык и региональные параметры и маркер открытого ключа подписанной сборки.</span><span class="sxs-lookup"><span data-stu-id="1420b-122">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1420b-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1420b-123">Child Elements</span></span>  
 <span data-ttu-id="1420b-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1420b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1420b-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1420b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1420b-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="1420b-126">Element</span></span>|<span data-ttu-id="1420b-127">Описание</span><span class="sxs-lookup"><span data-stu-id="1420b-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1420b-128">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="1420b-128">\<schemaImporterExtensions></span></span>|<span data-ttu-id="1420b-129">Содержит типы, используемые классом<xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="1420b-129">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1420b-130">Пример</span><span class="sxs-lookup"><span data-stu-id="1420b-130">Example</span></span>  
 <span data-ttu-id="1420b-131">В приведенном ниже примере кода добавляется тип расширения, который XmlSchemaImporter может использовать при сопоставлении типов.</span><span class="sxs-lookup"><span data-stu-id="1420b-131">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
       PublicKeyToken=b03f5f7f11d50a3a" />
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1420b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="1420b-132">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="1420b-133">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="1420b-133">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="1420b-134">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="1420b-134">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
