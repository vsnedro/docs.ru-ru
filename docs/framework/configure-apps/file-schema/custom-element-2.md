---
title: Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215478"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="49bbf-102">Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="49bbf-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="49bbf-103">Определяет параметры для пользовательских разделов конфигурации, использующих <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> классы и.</span><span class="sxs-lookup"><span data-stu-id="49bbf-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a><span data-ttu-id="49bbf-104">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="49bbf-104">Attributes</span></span>

<span data-ttu-id="49bbf-105">Нет</span><span class="sxs-lookup"><span data-stu-id="49bbf-105">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="49bbf-106">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="49bbf-106">Parent element</span></span>

|     | <span data-ttu-id="49bbf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="49bbf-107">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="49bbf-108">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49bbf-108">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="49bbf-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="49bbf-109">Child elements</span></span>

|     | <span data-ttu-id="49bbf-110">Описание</span><span class="sxs-lookup"><span data-stu-id="49bbf-110">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="49bbf-111">[**\<add>**](add-element-for-custom-2.md)для <xref:System.Configuration.NameValueSectionHandler> и<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="49bbf-111">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="49bbf-112">Добавляет настраиваемые параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="49bbf-112">Adds custom application settings.</span></span> |
| <span data-ttu-id="49bbf-113">[**\<remove>**](remove-element-for-custom-2.md)для <xref:System.Configuration.NameValueSectionHandler> и<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="49bbf-113">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="49bbf-114">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="49bbf-114">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="49bbf-115">[**\<clear>**](clear-element-for-custom-2.md)для <xref:System.Configuration.NameValueSectionHandler> и<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="49bbf-115">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="49bbf-116">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="49bbf-116">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="49bbf-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="49bbf-117">Remarks</span></span>

<span data-ttu-id="49bbf-118">**\<sectionName>** Элемент является пользовательским элементом, определяемым **\<section>** тегом в **\<configSections>** элементе.</span><span class="sxs-lookup"><span data-stu-id="49bbf-118">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="49bbf-119">В следующей таблице показан тип объекта, возвращаемого методом ConfigurationSettings. config для каждого обработчика раздела конфигурации:</span><span class="sxs-lookup"><span data-stu-id="49bbf-119">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="49bbf-120">Обработчик раздела конфигурации</span><span class="sxs-lookup"><span data-stu-id="49bbf-120">Configuration section handler</span></span>                        | <span data-ttu-id="49bbf-121">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="49bbf-121">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="49bbf-122">Пример</span><span class="sxs-lookup"><span data-stu-id="49bbf-122">Example</span></span>

<span data-ttu-id="49bbf-123">В следующем примере показано, как объявить разделы, в которых используются <xref:System.Configuration.DictionarySectionHandler> <xref:System.Configuration.NameValueSectionHandler> классы и.</span><span class="sxs-lookup"><span data-stu-id="49bbf-123">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="49bbf-124">Первый настраиваемый элемент — **\<dictionarySample>** , который содержит параметры, считанные <xref:System.Configuration.DictionarySectionHandler> классом в `System.dll` сборке.</span><span class="sxs-lookup"><span data-stu-id="49bbf-124">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="49bbf-125">Второй настраиваемый элемент — **\<mySection>** , который содержит параметры, считанные <xref:System.Configuration.NameValueSectionHandler> классом в `System.dll` сборке.</span><span class="sxs-lookup"><span data-stu-id="49bbf-125">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="49bbf-126">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="49bbf-126">Configuration file</span></span>

<span data-ttu-id="49bbf-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="49bbf-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="49bbf-128">См. также</span><span class="sxs-lookup"><span data-stu-id="49bbf-128">See also</span></span>

- [<span data-ttu-id="49bbf-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="49bbf-129">Configuration file schema for the .NET Framework</span></span>](index.md)
