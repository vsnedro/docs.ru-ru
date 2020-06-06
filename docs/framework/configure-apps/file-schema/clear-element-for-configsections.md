---
title: Элемент <clear> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155431"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="861d5-102">Элемент \<clear> для \<configSections></span><span class="sxs-lookup"><span data-stu-id="861d5-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="861d5-103">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="861d5-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="861d5-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="861d5-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="861d5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="861d5-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="861d5-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="861d5-106">Attribute</span></span>

|           | <span data-ttu-id="861d5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="861d5-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="861d5-108">**name**</span><span class="sxs-lookup"><span data-stu-id="861d5-108">**name**</span></span>  | <span data-ttu-id="861d5-109">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="861d5-109">Required attribute.</span></span><br><br><span data-ttu-id="861d5-110">Указывает имя раздела или группы разделов, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="861d5-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="861d5-111">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="861d5-111">Parent element</span></span>

|     | <span data-ttu-id="861d5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="861d5-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="861d5-113">**\<configSections>** Дерев</span><span class="sxs-lookup"><span data-stu-id="861d5-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="861d5-114">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="861d5-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="861d5-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="861d5-115">Child elements</span></span>

<span data-ttu-id="861d5-116">None</span><span class="sxs-lookup"><span data-stu-id="861d5-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="861d5-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="861d5-117">Remarks</span></span>

<span data-ttu-id="861d5-118">**\<clear>** Элемент удаляет все разделы и группы разделов из приложения, которые были определены ранее в текущем файле конфигурации или на более высоком уровне иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="861d5-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="861d5-119">Пример</span><span class="sxs-lookup"><span data-stu-id="861d5-119">Example</span></span>

<span data-ttu-id="861d5-120">В этом примере определяется файл конфигурации компьютера и файл конфигурации приложения, а также демонстрируется использование **\<clear>** элемента в файле конфигурации приложения для очистки разделов, ранее определенных в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="861d5-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="861d5-121">В следующем коде файла конфигурации компьютера объявляются два раздела **\<sampleSection>** и **\<anotherSampleSection>** , которые считываются перед файлом конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="861d5-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="861d5-122">В следующем коде файла конфигурации приложения очищаются все ранее объявленные разделы.</span><span class="sxs-lookup"><span data-stu-id="861d5-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="861d5-123">Приложение не может использовать или извлекать параметры в одном из разделов, объявленных в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="861d5-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="861d5-124">Однако он может использовать параметры из, **\<anotherSection>** так как он находится после **\<clear>** элемента.</span><span class="sxs-lookup"><span data-stu-id="861d5-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="861d5-125">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="861d5-125">Configuration file</span></span>

<span data-ttu-id="861d5-126">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="861d5-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="861d5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="861d5-127">See also</span></span>

- [<span data-ttu-id="861d5-128">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="861d5-128">Configuration file schema for the .NET Framework</span></span>](index.md)
