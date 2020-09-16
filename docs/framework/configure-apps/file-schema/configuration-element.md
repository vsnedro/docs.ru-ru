---
title: <configuration> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 8f79981a55d0bc9b1cd522e45f5606fda102c72c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544695"
---
# <a name="configuration-element"></a><span data-ttu-id="4a067-102">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="4a067-102">\<configuration> element</span></span>

<span data-ttu-id="4a067-103">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a067-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="4a067-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a067-104">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="4a067-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4a067-105">Attributes</span></span>

<span data-ttu-id="4a067-106">None</span><span class="sxs-lookup"><span data-stu-id="4a067-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="4a067-107">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="4a067-107">Parent element</span></span>

<span data-ttu-id="4a067-108">None</span><span class="sxs-lookup"><span data-stu-id="4a067-108">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="4a067-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4a067-109">Child elements</span></span>

|     | <span data-ttu-id="4a067-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4a067-110">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="4a067-111">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4a067-111">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="4a067-112">**\<startup>** Схема параметров</span><span class="sxs-lookup"><span data-stu-id="4a067-112">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="4a067-113">Все элементы в схеме параметров запуска.</span><span class="sxs-lookup"><span data-stu-id="4a067-113">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="4a067-114">**\<runtime>** Схема параметров</span><span class="sxs-lookup"><span data-stu-id="4a067-114">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="4a067-115">Все элементы в схеме параметров среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4a067-115">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="4a067-116">[**\<system.runtime.remoting>** Схема параметров](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4a067-116">[**\<system.runtime.remoting>** Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="4a067-117">Все элементы в схеме параметров удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="4a067-117">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="4a067-118">**\<system.Net>** Схема параметров</span><span class="sxs-lookup"><span data-stu-id="4a067-118">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="4a067-119">Все элементы в схеме параметров сети.</span><span class="sxs-lookup"><span data-stu-id="4a067-119">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="4a067-120">**\<cryptographySettings>** Схема параметров</span><span class="sxs-lookup"><span data-stu-id="4a067-120">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="4a067-121">Все элементы в схеме параметров шифрования.</span><span class="sxs-lookup"><span data-stu-id="4a067-121">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="4a067-122">**\<configuration>** Схема разделов</span><span class="sxs-lookup"><span data-stu-id="4a067-122">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="4a067-123">Все элементы в схеме параметров раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4a067-123">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="4a067-124">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="4a067-124">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="4a067-125">Все элементы в схеме параметров трассировки и отладки.</span><span class="sxs-lookup"><span data-stu-id="4a067-125">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="4a067-126">[Схема параметров конфигурации ASP.NET](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4a067-126">[ASP.NET Configuration Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="4a067-127">Все элементы в схеме конфигурации ASP.NET, включая элементы для настройки веб-сайтов и приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4a067-127">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="4a067-128">Используется в файлах *Web.config* .</span><span class="sxs-lookup"><span data-stu-id="4a067-128">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="4a067-129">[**\<webServices>** Схема параметров](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4a067-129">[**\<webServices>** Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="4a067-130">Все элементы в схеме параметров веб-служб.</span><span class="sxs-lookup"><span data-stu-id="4a067-130">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="4a067-131">Схема веб-параметров</span><span class="sxs-lookup"><span data-stu-id="4a067-131">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="4a067-132">Все элементы схемы веб-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS.</span><span class="sxs-lookup"><span data-stu-id="4a067-132">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="4a067-133">Используется в файлах *aspnet.config* .</span><span class="sxs-lookup"><span data-stu-id="4a067-133">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="4a067-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a067-134">Remarks</span></span>

<span data-ttu-id="4a067-135">Каждый файл конфигурации должен содержать ровно один **\<configuration>** элемент.</span><span class="sxs-lookup"><span data-stu-id="4a067-135">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a067-136">См. также</span><span class="sxs-lookup"><span data-stu-id="4a067-136">See also</span></span>

- [<span data-ttu-id="4a067-137">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4a067-137">Configuration file schema for the .NET Framework</span></span>](index.md)
