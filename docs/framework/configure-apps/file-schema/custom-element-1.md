---
title: Настраиваемый элемент для Синглетагсектионхандлер
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "80635398"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="c7f41-102">Настраиваемый элемент для Синглетагсектионхандлер</span><span class="sxs-lookup"><span data-stu-id="c7f41-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="c7f41-103">Определяет параметры в пользовательском разделе конфигурации, определяемом \<section> элементом, и использует <xref:System.Configuration.SingleTagSectionHandler> класс.</span><span class="sxs-lookup"><span data-stu-id="c7f41-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="c7f41-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="c7f41-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="c7f41-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7f41-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="c7f41-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c7f41-106">Attributes</span></span>

<span data-ttu-id="c7f41-107">Атрибуты и значения атрибутов определяются пользователем.</span><span class="sxs-lookup"><span data-stu-id="c7f41-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="c7f41-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="c7f41-108">Parent element</span></span>

|     | <span data-ttu-id="c7f41-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c7f41-109">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="c7f41-110">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c7f41-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c7f41-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c7f41-111">Child elements</span></span>

<span data-ttu-id="c7f41-112">None</span><span class="sxs-lookup"><span data-stu-id="c7f41-112">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c7f41-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c7f41-113">Remarks</span></span>

<span data-ttu-id="c7f41-114">**\<sectionName>** Элемент является пользовательским элементом, определяемым [**\<section>**](section-element.md) тегом в [**\<configSections>**](configsections-element-for-configuration.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="c7f41-114">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="c7f41-115">Система конфигурации возвращает <xref:System.Collections.IDictionary> объект при вызове метода <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c7f41-115">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="c7f41-116">Пример</span><span class="sxs-lookup"><span data-stu-id="c7f41-116">Example</span></span>

<span data-ttu-id="c7f41-117">В следующем примере объявляется пользовательский элемент с именем **\<sampleSection>** , который содержит параметры, считанные <xref:System.Configuration.SingleTagSectionHandler> классом:</span><span class="sxs-lookup"><span data-stu-id="c7f41-117">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="c7f41-118">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="c7f41-118">Configuration file</span></span>

<span data-ttu-id="c7f41-119">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , не находящимся на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="c7f41-119">This element can be used in the application configuration file, the machine configuration file (*Machine.config*), and *Web.config* files that aren't at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7f41-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c7f41-120">See also</span></span>

- [<span data-ttu-id="c7f41-121">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c7f41-121">Configuration file schema for the .NET Framework</span></span>](index.md)
