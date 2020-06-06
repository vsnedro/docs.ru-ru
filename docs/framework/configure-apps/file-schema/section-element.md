---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153738"
---
# <a name="section-element"></a><span data-ttu-id="42f74-102">Элемент \<section></span><span class="sxs-lookup"><span data-stu-id="42f74-102">\<section> element</span></span>

<span data-ttu-id="42f74-103">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42f74-103">Contains a configuration section declaration.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a><span data-ttu-id="42f74-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42f74-104">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="42f74-105">Требуемые атрибуты</span><span class="sxs-lookup"><span data-stu-id="42f74-105">Required attributes</span></span>

|           | <span data-ttu-id="42f74-106">Описание</span><span class="sxs-lookup"><span data-stu-id="42f74-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="42f74-107">**name**</span><span class="sxs-lookup"><span data-stu-id="42f74-107">**name**</span></span>  | <span data-ttu-id="42f74-108">Задает имя раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42f74-108">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="42f74-109">**type**</span><span class="sxs-lookup"><span data-stu-id="42f74-109">**type**</span></span>  | <span data-ttu-id="42f74-110">Указывает имя класса обработчика раздела конфигурации, считывающего раздел из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42f74-110">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="42f74-111">Значение типа имеет синтаксис "полное имя-раздела-класса-обработчика", простое-Assembly-Name ".</span><span class="sxs-lookup"><span data-stu-id="42f74-111">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="42f74-112">В качестве простого имени сборки используется имя корневого файла без расширения *DLL* .</span><span class="sxs-lookup"><span data-stu-id="42f74-112">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="42f74-113">Необязательные атрибуты</span><span class="sxs-lookup"><span data-stu-id="42f74-113">Optional attributes</span></span>

<span data-ttu-id="42f74-114">Следующие атрибуты применимы только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="42f74-114">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="42f74-115">Система конфигурации пропускает эти атрибуты для других типов приложений.</span><span class="sxs-lookup"><span data-stu-id="42f74-115">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="42f74-116">Описание</span><span class="sxs-lookup"><span data-stu-id="42f74-116">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="42f74-117">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="42f74-117">**allowDefinition**</span></span> | <span data-ttu-id="42f74-118">Указывает файл конфигурации, в котором может использоваться раздел.</span><span class="sxs-lookup"><span data-stu-id="42f74-118">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="42f74-119">Используйте одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="42f74-119">Use one of the following values:</span></span><br><br><span data-ttu-id="42f74-120">**Везде**</span><span class="sxs-lookup"><span data-stu-id="42f74-120">**Everywhere**</span></span><br><span data-ttu-id="42f74-121">Позволяет использовать раздел в любом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42f74-121">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="42f74-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="42f74-122">This is the default.</span></span><br><span data-ttu-id="42f74-123">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="42f74-123">**MachineOnly**</span></span><br><span data-ttu-id="42f74-124">Позволяет использовать раздел только в файле конфигурации компьютера (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="42f74-124">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="42f74-125">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="42f74-125">**MachineToApplication**</span></span><br><span data-ttu-id="42f74-126">Позволяет использовать раздел в файле конфигурации компьютера или файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="42f74-126">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="42f74-127">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="42f74-127">**allowLocation**</span></span>   | <span data-ttu-id="42f74-128">Определяет, можно ли использовать раздел в **\<location>** элементе.</span><span class="sxs-lookup"><span data-stu-id="42f74-128">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="42f74-129">Используйте одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="42f74-129">Use one of the following values:</span></span><br><br><span data-ttu-id="42f74-130">**true**</span><span class="sxs-lookup"><span data-stu-id="42f74-130">**true**</span></span><br><span data-ttu-id="42f74-131">Позволяет использовать раздел внутри **\<location>** элемента.</span><span class="sxs-lookup"><span data-stu-id="42f74-131">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="42f74-132">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="42f74-132">This is the default.</span></span><br><span data-ttu-id="42f74-133">**false**</span><span class="sxs-lookup"><span data-stu-id="42f74-133">**false**</span></span><br><span data-ttu-id="42f74-134">Не позволяет использовать раздел внутри **\<location>** элемента.</span><span class="sxs-lookup"><span data-stu-id="42f74-134">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="42f74-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42f74-135">Parent elements</span></span>

|     | <span data-ttu-id="42f74-136">Описание</span><span class="sxs-lookup"><span data-stu-id="42f74-136">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="42f74-137">**\<configSections>** Дерев</span><span class="sxs-lookup"><span data-stu-id="42f74-137">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="42f74-138">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="42f74-138">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="42f74-139">**\<sectionGroup>** Дерев</span><span class="sxs-lookup"><span data-stu-id="42f74-139">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="42f74-140">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42f74-140">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="42f74-141">**\<section>** Элемент — это дочерний элемент либо, либо, **\<configSections>** **\<sectionGroup>** но не оба.</span><span class="sxs-lookup"><span data-stu-id="42f74-141">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="42f74-142">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42f74-142">Child elements</span></span>

<span data-ttu-id="42f74-143">None</span><span class="sxs-lookup"><span data-stu-id="42f74-143">None</span></span>

## <a name="remarks"></a><span data-ttu-id="42f74-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="42f74-144">Remarks</span></span>

<span data-ttu-id="42f74-145">Объявление раздела конфигурации фактически определяет новый элемент для файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42f74-145">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="42f74-146">Новый элемент содержит параметры, которые обработчик раздела конфигурации (то есть класс, реализующий <xref:System.Configuration.IConfigurationSectionHandler> интерфейс) считывает.</span><span class="sxs-lookup"><span data-stu-id="42f74-146">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="42f74-147">Атрибуты и дочерние элементы определяемого раздела зависят от обработчика раздела, используемого для чтения параметров.</span><span class="sxs-lookup"><span data-stu-id="42f74-147">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="42f74-148">Объявление обработчика раздела конфигурации в файле *Machine. config* позволяет использовать раздел конфигурации в любом файле конфигурации приложения на этом компьютере, если в атрибуте **allowDefinition** не указано иное.</span><span class="sxs-lookup"><span data-stu-id="42f74-148">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="42f74-149">Пример</span><span class="sxs-lookup"><span data-stu-id="42f74-149">Example</span></span>

<span data-ttu-id="42f74-150">В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="42f74-150">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler"
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="42f74-151">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="42f74-151">Configuration file</span></span>

<span data-ttu-id="42f74-152">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="42f74-152">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="42f74-153">См. также</span><span class="sxs-lookup"><span data-stu-id="42f74-153">See also</span></span>

- [<span data-ttu-id="42f74-154">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="42f74-154">Configuration file schema for the .NET Framework</span></span>](index.md)
