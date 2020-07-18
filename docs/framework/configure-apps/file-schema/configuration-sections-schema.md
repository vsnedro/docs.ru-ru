---
title: Схема разделов конфигурации
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: fc43a9c32ba33629b6e89120cf57f6d212ab3a56
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441665"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="1d254-102">Схема разделов конфигурации</span><span class="sxs-lookup"><span data-stu-id="1d254-102">Configuration sections schema</span></span>

<span data-ttu-id="1d254-103">Схема разделов конфигурации содержит элементы, определяющие пользовательские параметры в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d254-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="1d254-104">Общие сведения о файлах конфигурации и схемах см. [в разделе Схема файла конфигурации для .NET Framework](index.md).</span><span class="sxs-lookup"><span data-stu-id="1d254-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="1d254-105">Описание</span><span class="sxs-lookup"><span data-stu-id="1d254-105">Description</span></span> |
| --- | ----------- |
| [**\<configSections>**](configsections-element-for-configuration.md) | <span data-ttu-id="1d254-106">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="1d254-106">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="1d254-107">**\<section>** для **\<configSections>** и**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="1d254-107">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="1d254-108">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d254-108">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="1d254-109">**\<sectionGroup>** предмет**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="1d254-109">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="1d254-110">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d254-110">Defines a namespace for configuration sections.</span></span> |

<a name="dep"></a>

## <a name="unimplemented-elements"></a><span data-ttu-id="1d254-111">Нереализованные элементы</span><span class="sxs-lookup"><span data-stu-id="1d254-111">Unimplemented elements</span></span>

<span data-ttu-id="1d254-112">Следующие элементы не влияют на использование и не должны использоваться:</span><span class="sxs-lookup"><span data-stu-id="1d254-112">The following elements have no impact and should not be used:</span></span>

* **\<clear>**
* **\<remove>**
