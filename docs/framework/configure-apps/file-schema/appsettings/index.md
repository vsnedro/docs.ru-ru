---
title: Схема параметров приложения
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a67689bd9757f7586881fd910ef6103b1dffeab8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550453"
---
# <a name="app-settings-schema"></a><span data-ttu-id="65e22-102">Схема параметров приложения</span><span class="sxs-lookup"><span data-stu-id="65e22-102">App Settings schema</span></span>

<span data-ttu-id="65e22-103">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="65e22-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="65e22-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="65e22-104">Element</span></span> | <span data-ttu-id="65e22-105">Описание</span><span class="sxs-lookup"><span data-stu-id="65e22-105">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="65e22-106">Содержит **\<add>** **\<clear>** теги, и **\<remove>** для управления параметрами приложения.</span><span class="sxs-lookup"><span data-stu-id="65e22-106">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="65e22-107">Имеет необязательный атрибут **file**.</span><span class="sxs-lookup"><span data-stu-id="65e22-107">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="65e22-108">Определяет параметр.</span><span class="sxs-lookup"><span data-stu-id="65e22-108">Defines a setting.</span></span> <span data-ttu-id="65e22-109">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="65e22-109">Child of **\<appSettings>**.</span></span> <span data-ttu-id="65e22-110">Обязательные атрибуты — **key** и **value**.</span><span class="sxs-lookup"><span data-stu-id="65e22-110">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="65e22-111">Удаляет все параметры.</span><span class="sxs-lookup"><span data-stu-id="65e22-111">Clears all settings.</span></span> <span data-ttu-id="65e22-112">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="65e22-112">Child of **\<appSettings>**.</span></span> <span data-ttu-id="65e22-113">Не имеет атрибутов.</span><span class="sxs-lookup"><span data-stu-id="65e22-113">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="65e22-114">Удаляет параметр.</span><span class="sxs-lookup"><span data-stu-id="65e22-114">Removes a setting.</span></span> <span data-ttu-id="65e22-115">Дочерний элемент **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="65e22-115">Child of **\<appSettings>**.</span></span> <span data-ttu-id="65e22-116">Требуется атрибут **key**.</span><span class="sxs-lookup"><span data-stu-id="65e22-116">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="65e22-117">\<appSettings> - элемент</span><span class="sxs-lookup"><span data-stu-id="65e22-117">\<appSettings> element</span></span>

<span data-ttu-id="65e22-118">Этот элемент содержит **\<add>** **\<clear>** теги, и **\<remove>** для управления параметрами приложения.</span><span class="sxs-lookup"><span data-stu-id="65e22-118">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="65e22-119">Определяет необязательный атрибут для **file**.</span><span class="sxs-lookup"><span data-stu-id="65e22-119">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="65e22-120">\<add> - элемент</span><span class="sxs-lookup"><span data-stu-id="65e22-120">\<add> element</span></span>

<span data-ttu-id="65e22-121">Добавляет пользовательский параметр приложения в виде пары "имя-значение" в коллекцию параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="65e22-121">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="65e22-122">Определяет атрибуты для **key** и **value**.</span><span class="sxs-lookup"><span data-stu-id="65e22-122">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="65e22-123">\<clear> - элемент</span><span class="sxs-lookup"><span data-stu-id="65e22-123">\<clear> element</span></span>

<span data-ttu-id="65e22-124">Удаляет все ссылки на унаследованные пользовательские параметры приложения и разрешает только ссылки, добавленные **\<add>** элементами после **\<clear>** элемента.</span><span class="sxs-lookup"><span data-stu-id="65e22-124">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="65e22-125">Атрибуты не определяются.</span><span class="sxs-lookup"><span data-stu-id="65e22-125">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="65e22-126">\<remove> - элемент</span><span class="sxs-lookup"><span data-stu-id="65e22-126">\<remove> element</span></span>

<span data-ttu-id="65e22-127">Удаляет ссылку на унаследованный пользовательский параметр приложения из коллекции параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="65e22-127">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="65e22-128">Определяет атрибут для **key**.</span><span class="sxs-lookup"><span data-stu-id="65e22-128">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="65e22-129">Пример</span><span class="sxs-lookup"><span data-stu-id="65e22-129">Example</span></span>

<span data-ttu-id="65e22-130">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="65e22-130">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="65e22-131">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="65e22-131">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="65e22-132">См. также</span><span class="sxs-lookup"><span data-stu-id="65e22-132">See also</span></span>

- [<span data-ttu-id="65e22-133">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="65e22-133">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="65e22-134">Архитектура параметров приложения</span><span class="sxs-lookup"><span data-stu-id="65e22-134">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
