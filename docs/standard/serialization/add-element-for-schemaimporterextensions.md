---
title: Элемент <add> для <schemaImporterExtensions>
description: Элемент <add> добавляет типы, используемые классом XmlSchemaImporter для сопоставления типов XSD с типами .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 6fd8113ad39a22c927035fca574151ae8f002685
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84288333"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="38975-103">Элемент \<add> для \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="38975-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="38975-104">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter>, для сопоставления типов XSD с типами платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38975-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="38975-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="38975-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="38975-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38975-106">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38975-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38975-107">Attributes and Elements</span></span>  
 <span data-ttu-id="38975-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="38975-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38975-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38975-109">Attributes</span></span>  
  
|<span data-ttu-id="38975-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="38975-110">Attribute</span></span>|<span data-ttu-id="38975-111">Описание</span><span class="sxs-lookup"><span data-stu-id="38975-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38975-112">**name**</span><span class="sxs-lookup"><span data-stu-id="38975-112">**name**</span></span>|<span data-ttu-id="38975-113">Простое имя, используемое для поиска экземпляра.</span><span class="sxs-lookup"><span data-stu-id="38975-113">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="38975-114">**type**</span><span class="sxs-lookup"><span data-stu-id="38975-114">**type**</span></span>|<span data-ttu-id="38975-115">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="38975-115">Required.</span></span> <span data-ttu-id="38975-116">Задает добавляемый класс расширения схемы.</span><span class="sxs-lookup"><span data-stu-id="38975-116">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="38975-117">Значение атрибута **type** должно располагаться на одной строке и содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="38975-117">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="38975-118">Когда сборка помещается в глобальный кэш сборок (GAC), она должна также содержать версию, язык и региональные параметры и маркер открытого ключа подписанной сборки.</span><span class="sxs-lookup"><span data-stu-id="38975-118">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38975-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38975-119">Child Elements</span></span>  
 <span data-ttu-id="38975-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="38975-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38975-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38975-121">Parent Elements</span></span>  
  
|<span data-ttu-id="38975-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="38975-122">Element</span></span>|<span data-ttu-id="38975-123">Описание</span><span class="sxs-lookup"><span data-stu-id="38975-123">Description</span></span>|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|<span data-ttu-id="38975-124">Содержит типы, используемые классом<xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="38975-124">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="38975-125">Пример</span><span class="sxs-lookup"><span data-stu-id="38975-125">Example</span></span>  
 <span data-ttu-id="38975-126">В приведенном ниже примере кода добавляется тип расширения, который XmlSchemaImporter может использовать при сопоставлении типов.</span><span class="sxs-lookup"><span data-stu-id="38975-126">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="38975-127">См. также</span><span class="sxs-lookup"><span data-stu-id="38975-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="38975-128">\<system.xml.serialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="38975-128">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="38975-129">\<schemaImporterExtensions> Элемент</span><span class="sxs-lookup"><span data-stu-id="38975-129">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
