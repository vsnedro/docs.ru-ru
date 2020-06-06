---
title: Элемент <remove> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: 83abbdbf0d3e4dfd16c0e8c649200c4ecc7329f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215496"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="5ef81-102">Элемент \<remove> для \<appSettings></span><span class="sxs-lookup"><span data-stu-id="5ef81-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="5ef81-103">Удаляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="5ef81-103">Removes custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="5ef81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ef81-104">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="5ef81-105">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ef81-105">Attribute</span></span>

|         | <span data-ttu-id="5ef81-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5ef81-106">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="5ef81-107">**key**</span><span class="sxs-lookup"><span data-stu-id="5ef81-107">**key**</span></span> | <span data-ttu-id="5ef81-108">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="5ef81-108">Required attribute.</span></span><br><br><span data-ttu-id="5ef81-109">Задает имя удаляемого ключа.</span><span class="sxs-lookup"><span data-stu-id="5ef81-109">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="5ef81-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="5ef81-110">Parent element</span></span>

|     | <span data-ttu-id="5ef81-111">Описание</span><span class="sxs-lookup"><span data-stu-id="5ef81-111">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="5ef81-112">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5ef81-112">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5ef81-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5ef81-113">Child elements</span></span>

<span data-ttu-id="5ef81-114">None</span><span class="sxs-lookup"><span data-stu-id="5ef81-114">None</span></span>

## <a name="example"></a><span data-ttu-id="5ef81-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5ef81-115">Example</span></span>

<span data-ttu-id="5ef81-116">В следующем примере показано, как удалить настраиваемый параметр конфигурации для `ApplicationName` :</span><span class="sxs-lookup"><span data-stu-id="5ef81-116">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="5ef81-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5ef81-117">See also</span></span>

- [<span data-ttu-id="5ef81-118">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5ef81-118">Configuration file schema for the .NET Framework</span></span>](../index.md)
