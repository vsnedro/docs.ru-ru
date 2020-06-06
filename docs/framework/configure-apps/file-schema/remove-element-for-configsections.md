---
title: Элемент <remove> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154534"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="ad3af-102">Элемент \<remove> для \<configSections></span><span class="sxs-lookup"><span data-stu-id="ad3af-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="ad3af-103">Удаляет предопределенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="ad3af-103">Removes a predefined section or section group.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="ad3af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad3af-104">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="ad3af-105">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ad3af-105">Attribute</span></span>

|           | <span data-ttu-id="ad3af-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ad3af-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ad3af-107">**name**</span><span class="sxs-lookup"><span data-stu-id="ad3af-107">**name**</span></span>  | <span data-ttu-id="ad3af-108">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ad3af-108">Required attribute.</span></span><br><br><span data-ttu-id="ad3af-109">Указывает имя раздела или группы разделов, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="ad3af-109">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ad3af-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="ad3af-110">Parent element</span></span>

|     | <span data-ttu-id="ad3af-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ad3af-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ad3af-112">**\<configSections>** Дерев</span><span class="sxs-lookup"><span data-stu-id="ad3af-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="ad3af-113">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="ad3af-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ad3af-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad3af-114">Child elements</span></span>

<span data-ttu-id="ad3af-115">None</span><span class="sxs-lookup"><span data-stu-id="ad3af-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ad3af-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad3af-116">Remarks</span></span>

<span data-ttu-id="ad3af-117">Элемент можно использовать **\<remove>** для удаления разделов и групп разделов из приложения, которые были определены на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ad3af-117">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="ad3af-118">Пример</span><span class="sxs-lookup"><span data-stu-id="ad3af-118">Example</span></span>

<span data-ttu-id="ad3af-119">В следующем примере показано, как использовать **\<remove>** элемент в файле конфигурации приложения для удаления раздела, ранее определенного в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="ad3af-119">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="ad3af-120">Следующий код файла конфигурации компьютера объявляет раздел **\<sampleSection>** :</span><span class="sxs-lookup"><span data-stu-id="ad3af-120">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
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

<span data-ttu-id="ad3af-121">Следующий код файла конфигурации приложения удаляет **\<sampleSection>** раздел.</span><span class="sxs-lookup"><span data-stu-id="ad3af-121">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="ad3af-122">После удаления приложение не сможет получить параметры в **\<sampleSection>** .</span><span class="sxs-lookup"><span data-stu-id="ad3af-122">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ad3af-123">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="ad3af-123">Configuration file</span></span>

<span data-ttu-id="ad3af-124">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="ad3af-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad3af-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ad3af-125">See also</span></span>

- [<span data-ttu-id="ad3af-126">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ad3af-126">Configuration file schema for the .NET Framework</span></span>](index.md)
