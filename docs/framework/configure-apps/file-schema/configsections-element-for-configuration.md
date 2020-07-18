---
title: Элемент <configSections> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 1e4bb7a7cfb0b140ca6d13c162708c3c30bd496d
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441691"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="10e24-102">Элемент \<configSections> для \<configuration></span><span class="sxs-lookup"><span data-stu-id="10e24-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="10e24-103">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="10e24-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="10e24-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="10e24-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="10e24-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="10e24-105">Attributes</span></span>

<span data-ttu-id="10e24-106">Нет</span><span class="sxs-lookup"><span data-stu-id="10e24-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="10e24-107">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="10e24-107">Parent element</span></span>

|     | <span data-ttu-id="10e24-108">Описание</span><span class="sxs-lookup"><span data-stu-id="10e24-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="10e24-109">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="10e24-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="10e24-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="10e24-110">Child elements</span></span>

|     | <span data-ttu-id="10e24-111">Описание</span><span class="sxs-lookup"><span data-stu-id="10e24-111">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="10e24-112">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="10e24-112">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="10e24-113">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="10e24-113">Defines a namespace for configuration sections.</span></span> |

## <a name="remarks"></a><span data-ttu-id="10e24-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="10e24-114">Remarks</span></span>

<span data-ttu-id="10e24-115">Если этот элемент находится в файле конфигурации, он должен быть первым дочерним элементом **\<configuration>** элемента.</span><span class="sxs-lookup"><span data-stu-id="10e24-115">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="10e24-116">Пример</span><span class="sxs-lookup"><span data-stu-id="10e24-116">Example</span></span>

<span data-ttu-id="10e24-117">В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="10e24-117">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="10e24-118">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="10e24-118">Configuration file</span></span>

<span data-ttu-id="10e24-119">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*) и *Web.config* файлах, которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="10e24-119">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="10e24-120">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="10e24-120">See also</span></span>

- [<span data-ttu-id="10e24-121">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="10e24-121">Configuration file schema for the .NET Framework</span></span>](index.md)
