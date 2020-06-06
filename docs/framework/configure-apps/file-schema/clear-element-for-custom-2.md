---
title: <clear>элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214743"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="1ed97-102">\<clear>элемент для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="1ed97-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="1ed97-103">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="1ed97-103">Clears all previously defined settings in a section.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="1ed97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ed97-104">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="1ed97-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ed97-105">Attributes</span></span>

<span data-ttu-id="1ed97-106">Нет</span><span class="sxs-lookup"><span data-stu-id="1ed97-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="1ed97-107">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="1ed97-107">Parent element</span></span>

|     | <span data-ttu-id="1ed97-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1ed97-108">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="1ed97-109">**\<sectionName>** Дерев</span><span class="sxs-lookup"><span data-stu-id="1ed97-109">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="1ed97-110">Определяет параметры для пользовательских разделов конфигурации, использующих <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> классы и.</span><span class="sxs-lookup"><span data-stu-id="1ed97-110">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1ed97-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ed97-111">Child elements</span></span>

<span data-ttu-id="1ed97-112">None</span><span class="sxs-lookup"><span data-stu-id="1ed97-112">None</span></span>

## <a name="remarks"></a><span data-ttu-id="1ed97-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ed97-113">Remarks</span></span>

<span data-ttu-id="1ed97-114">С помощью элемента можно **\<clear>** удалить из приложения все параметры, которые были определены на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1ed97-114">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="1ed97-115">Пример</span><span class="sxs-lookup"><span data-stu-id="1ed97-115">Example</span></span>

<span data-ttu-id="1ed97-116">В этом примере определяется файл конфигурации компьютера и файл конфигурации приложения, а также демонстрируется использование **\<clear>** элемента в файле конфигурации приложения для очистки разделов, ранее определенных в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="1ed97-116">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="1ed97-117">Следующий код файла конфигурации компьютера объявляет раздел **\<mySection>** :</span><span class="sxs-lookup"><span data-stu-id="1ed97-117">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="1ed97-118">Следующий код файла конфигурации приложения удаляет все параметры из **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="1ed97-118">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="1ed97-119">Приложение не может получить параметры, которые были объявлены в в **\<mySection>** разделе файла конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="1ed97-119">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="1ed97-120">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="1ed97-120">Configuration file</span></span>

<span data-ttu-id="1ed97-121">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="1ed97-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ed97-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1ed97-122">See also</span></span>

- [<span data-ttu-id="1ed97-123">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1ed97-123">Configuration file schema for the .NET Framework</span></span>](index.md)
