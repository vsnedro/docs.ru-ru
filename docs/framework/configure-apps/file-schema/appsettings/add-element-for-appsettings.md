---
title: Элемент <add> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214812"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="994ed-102">Элемент \<add> для \<appSettings></span><span class="sxs-lookup"><span data-stu-id="994ed-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="994ed-103">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="994ed-103">Adds a custom application setting.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="994ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="994ed-104">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="994ed-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="994ed-105">Attributes</span></span>

|           | <span data-ttu-id="994ed-106">Описание</span><span class="sxs-lookup"><span data-stu-id="994ed-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="994ed-107">**key**</span><span class="sxs-lookup"><span data-stu-id="994ed-107">**key**</span></span>   | <span data-ttu-id="994ed-108">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="994ed-108">Required attribute.</span></span><br><br><span data-ttu-id="994ed-109">Указывает имя добавляемого ключа.</span><span class="sxs-lookup"><span data-stu-id="994ed-109">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="994ed-110">**value**</span><span class="sxs-lookup"><span data-stu-id="994ed-110">**value**</span></span> | <span data-ttu-id="994ed-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="994ed-111">Required attribute.</span></span><br><br><span data-ttu-id="994ed-112">Указывает значение добавляемого ключа.</span><span class="sxs-lookup"><span data-stu-id="994ed-112">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="994ed-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="994ed-113">Parent element</span></span>

|     | <span data-ttu-id="994ed-114">Описание</span><span class="sxs-lookup"><span data-stu-id="994ed-114">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="994ed-115">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="994ed-115">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="994ed-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="994ed-116">Child elements</span></span>

<span data-ttu-id="994ed-117">None</span><span class="sxs-lookup"><span data-stu-id="994ed-117">None</span></span>

## <a name="example"></a><span data-ttu-id="994ed-118">Пример</span><span class="sxs-lookup"><span data-stu-id="994ed-118">Example</span></span>

<span data-ttu-id="994ed-119">В следующем примере показано, как добавить настраиваемый параметр конфигурации для имени приложения:</span><span class="sxs-lookup"><span data-stu-id="994ed-119">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="994ed-120">В следующем примере элемент используется `<add>` для определения двух параметров совместимости в приложении ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="994ed-120">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="994ed-121">См. также</span><span class="sxs-lookup"><span data-stu-id="994ed-121">See also</span></span>

- [<span data-ttu-id="994ed-122">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="994ed-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
