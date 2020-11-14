---
title: Элемент <add> для <schemaImporterExtensions>
description: Элемент <add> добавляет типы, используемые классом XmlSchemaImporter для сопоставления типов XSD с типами .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 38d8ebd6e973632b23865ad60e007d9aa21e7da6
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282005"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="c587e-103">Элемент \<add> для \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c587e-103">\<add> Element for \<schemaImporterExtensions></span></span>

<span data-ttu-id="c587e-104">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter>, для сопоставления типов XSD с типами .NET.</span><span class="sxs-lookup"><span data-stu-id="c587e-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET types.</span></span> <span data-ttu-id="c587e-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="c587e-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
\<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="c587e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c587e-106">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c587e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c587e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c587e-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c587e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c587e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c587e-109">Attributes</span></span>  
  
|<span data-ttu-id="c587e-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c587e-110">Attribute</span></span>|<span data-ttu-id="c587e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="c587e-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c587e-112">**name**</span><span class="sxs-lookup"><span data-stu-id="c587e-112">**name**</span></span>|<span data-ttu-id="c587e-113">Простое имя, используемое для поиска экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c587e-113">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="c587e-114">**type**</span><span class="sxs-lookup"><span data-stu-id="c587e-114">**type**</span></span>|<span data-ttu-id="c587e-115">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c587e-115">Required.</span></span> <span data-ttu-id="c587e-116">Задает добавляемый класс расширения схемы.</span><span class="sxs-lookup"><span data-stu-id="c587e-116">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="c587e-117">Значение атрибута **type** должно располагаться на одной строке и содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="c587e-117">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="c587e-118">Когда сборка помещается в глобальный кэш сборок (GAC), она должна также содержать версию, язык и региональные параметры и маркер открытого ключа подписанной сборки.</span><span class="sxs-lookup"><span data-stu-id="c587e-118">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c587e-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c587e-119">Child Elements</span></span>  
 <span data-ttu-id="c587e-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c587e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c587e-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c587e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c587e-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="c587e-122">Element</span></span>|<span data-ttu-id="c587e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c587e-123">Description</span></span>|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|<span data-ttu-id="c587e-124">Содержит типы, используемые классом<xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="c587e-124">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c587e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="c587e-125">Example</span></span>  
 <span data-ttu-id="c587e-126">В приведенном ниже примере кода добавляется тип расширения, который XmlSchemaImporter может использовать при сопоставлении типов.</span><span class="sxs-lookup"><span data-stu-id="c587e-126">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c587e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c587e-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="c587e-128">\<system.xml.serialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="c587e-128">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="c587e-129">\<schemaImporterExtensions> Элемент</span><span class="sxs-lookup"><span data-stu-id="c587e-129">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
