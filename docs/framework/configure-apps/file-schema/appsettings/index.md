---
title: Схема параметров приложения
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: 0a3363b35a6fc8bd27753eb034f8a1e95feb5292
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215431"
---
# <a name="app-settings-schema"></a><span data-ttu-id="e1eea-102">Схема параметров приложения</span><span class="sxs-lookup"><span data-stu-id="e1eea-102">App Settings schema</span></span>

<span data-ttu-id="e1eea-103">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e1eea-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="e1eea-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1eea-104">Element</span></span> | <span data-ttu-id="e1eea-105">Описание</span><span class="sxs-lookup"><span data-stu-id="e1eea-105">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="e1eea-106">Содержит **\<add>** **\<clear>** теги, и **\<remove>** для управления параметрами приложения.</span><span class="sxs-lookup"><span data-stu-id="e1eea-106">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="e1eea-107">Имеет необязательный атрибут **file**.</span><span class="sxs-lookup"><span data-stu-id="e1eea-107">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="e1eea-108">Определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="e1eea-108">Defines a setting.</span></span> <span data-ttu-id="e1eea-109">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="e1eea-109">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e1eea-110">Обязательные атрибуты — **key** и **value**.</span><span class="sxs-lookup"><span data-stu-id="e1eea-110">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="e1eea-111">Удаляет все параметры.</span><span class="sxs-lookup"><span data-stu-id="e1eea-111">Clears all settings.</span></span> <span data-ttu-id="e1eea-112">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="e1eea-112">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e1eea-113">Не имеет атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e1eea-113">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="e1eea-114">Удаляет параметр.</span><span class="sxs-lookup"><span data-stu-id="e1eea-114">Removes a setting.</span></span> <span data-ttu-id="e1eea-115">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="e1eea-115">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e1eea-116">Требуется атрибут **key**.</span><span class="sxs-lookup"><span data-stu-id="e1eea-116">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="e1eea-117">\<appSettings> - элемент</span><span class="sxs-lookup"><span data-stu-id="e1eea-117">\<appSettings> element</span></span>

<span data-ttu-id="e1eea-118">Этот элемент содержит **\<add>** **\<clear>** теги, и **\<remove>** для управления параметрами приложения.</span><span class="sxs-lookup"><span data-stu-id="e1eea-118">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="e1eea-119">Определяет необязательный атрибут для **file**.</span><span class="sxs-lookup"><span data-stu-id="e1eea-119">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="e1eea-120">\<add> - элемент</span><span class="sxs-lookup"><span data-stu-id="e1eea-120">\<add> element</span></span>

<span data-ttu-id="e1eea-121">Добавляет пользовательский параметр приложения в виде пары "имя-значение" в коллекцию параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="e1eea-121">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="e1eea-122">Определяет атрибуты для **key** и **value**.</span><span class="sxs-lookup"><span data-stu-id="e1eea-122">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="e1eea-123">Элемент \<clear></span><span class="sxs-lookup"><span data-stu-id="e1eea-123">\<clear> element</span></span>

<span data-ttu-id="e1eea-124">Удаляет все ссылки на унаследованные пользовательские параметры приложения и разрешает только ссылки, добавленные **\<add>** элементами после **\<clear>** элемента.</span><span class="sxs-lookup"><span data-stu-id="e1eea-124">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="e1eea-125">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="e1eea-125">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="e1eea-126">Элемент \<remove></span><span class="sxs-lookup"><span data-stu-id="e1eea-126">\<remove> element</span></span>

<span data-ttu-id="e1eea-127">Удаляет ссылку на унаследованный пользовательский параметр приложения из коллекции параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="e1eea-127">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="e1eea-128">Определяет атрибут для **key**.</span><span class="sxs-lookup"><span data-stu-id="e1eea-128">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="e1eea-129">Пример</span><span class="sxs-lookup"><span data-stu-id="e1eea-129">Example</span></span>

<span data-ttu-id="e1eea-130">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="e1eea-130">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="e1eea-131">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="e1eea-131">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e1eea-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e1eea-132">See also</span></span>

- [<span data-ttu-id="e1eea-133">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="e1eea-133">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="e1eea-134">Архитектура параметров приложения</span><span class="sxs-lookup"><span data-stu-id="e1eea-134">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
