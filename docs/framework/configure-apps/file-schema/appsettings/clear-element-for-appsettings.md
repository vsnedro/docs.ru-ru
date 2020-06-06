---
title: Элемент <clear> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214800"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="9fc65-102">Элемент \<clear> для \<appSettings></span><span class="sxs-lookup"><span data-stu-id="9fc65-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="9fc65-103">Удаляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="9fc65-103">Clears custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="9fc65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fc65-104">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="9fc65-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9fc65-105">Attributes</span></span>

<span data-ttu-id="9fc65-106">Нет</span><span class="sxs-lookup"><span data-stu-id="9fc65-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="9fc65-107">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="9fc65-107">Parent element</span></span>

|     | <span data-ttu-id="9fc65-108">Описание</span><span class="sxs-lookup"><span data-stu-id="9fc65-108">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="9fc65-109">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML или другие сведения о конфигурации пользовательских приложений.</span><span class="sxs-lookup"><span data-stu-id="9fc65-109">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9fc65-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9fc65-110">Child elements</span></span>

<span data-ttu-id="9fc65-111">None</span><span class="sxs-lookup"><span data-stu-id="9fc65-111">None</span></span>

## <a name="example"></a><span data-ttu-id="9fc65-112">Пример</span><span class="sxs-lookup"><span data-stu-id="9fc65-112">Example</span></span>

<span data-ttu-id="9fc65-113">В следующем примере показано, как удалить настраиваемые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9fc65-113">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="9fc65-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9fc65-114">See also</span></span>

- [<span data-ttu-id="9fc65-115">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9fc65-115">Configuration file schema for the .NET Framework</span></span>](../index.md)
