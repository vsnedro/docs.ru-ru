---
title: <add>элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215440"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="65e2f-102">\<add>элемент для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="65e2f-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="65e2f-103">Добавляет настраиваемые параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="65e2f-103">Adds custom application settings.</span></span> <span data-ttu-id="65e2f-104">Каждый **\<add>** тег содержит пару "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="65e2f-104">Each **\<add>** tag contains a key/value pair.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="65e2f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65e2f-105">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="65e2f-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="65e2f-106">Attributes</span></span>

| <span data-ttu-id="65e2f-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="65e2f-107">Attribute</span></span> | <span data-ttu-id="65e2f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="65e2f-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="65e2f-109">**key**</span><span class="sxs-lookup"><span data-stu-id="65e2f-109">**key**</span></span>   | <span data-ttu-id="65e2f-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="65e2f-110">Required attribute.</span></span><br><br><span data-ttu-id="65e2f-111">Задает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="65e2f-111">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="65e2f-112">**value**</span><span class="sxs-lookup"><span data-stu-id="65e2f-112">**value**</span></span> | <span data-ttu-id="65e2f-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="65e2f-113">Required attribute.</span></span><br><br><span data-ttu-id="65e2f-114">Задает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="65e2f-114">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="65e2f-115">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="65e2f-115">Parent element</span></span>

| <span data-ttu-id="65e2f-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="65e2f-116">Element</span></span> | <span data-ttu-id="65e2f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="65e2f-117">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="65e2f-118">**\<sectionName>** Дерев</span><span class="sxs-lookup"><span data-stu-id="65e2f-118">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="65e2f-119">Определяет параметры для пользовательских разделов конфигурации, использующих <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> классы и.</span><span class="sxs-lookup"><span data-stu-id="65e2f-119">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="65e2f-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="65e2f-120">Child elements</span></span>

<span data-ttu-id="65e2f-121">None</span><span class="sxs-lookup"><span data-stu-id="65e2f-121">None</span></span>

## <a name="example"></a><span data-ttu-id="65e2f-122">Пример</span><span class="sxs-lookup"><span data-stu-id="65e2f-122">Example</span></span>

<span data-ttu-id="65e2f-123">В следующем примере показано, как определить пользовательский раздел конфигурации и использовать **\<add>** элемент для помещения параметров в раздел:</span><span class="sxs-lookup"><span data-stu-id="65e2f-123">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="65e2f-124">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="65e2f-124">Configuration file</span></span>

<span data-ttu-id="65e2f-125">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="65e2f-125">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="65e2f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="65e2f-126">See also</span></span>

- [<span data-ttu-id="65e2f-127">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="65e2f-127">Configuration file schema for the .NET Framework</span></span>](index.md)
