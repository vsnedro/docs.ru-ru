---
title: Элемент <assemblyBinding> для <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155483"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="82d4f-102">Элемент \<assemblyBinding> для \<configuration></span><span class="sxs-lookup"><span data-stu-id="82d4f-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="82d4f-103">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="82d4f-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="82d4f-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="82d4f-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="82d4f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82d4f-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="82d4f-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="82d4f-106">Attribute</span></span>

|           | <span data-ttu-id="82d4f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="82d4f-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="82d4f-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="82d4f-108">**xmlns**</span></span> | <span data-ttu-id="82d4f-109">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="82d4f-109">Required attribute.</span></span><br><br><span data-ttu-id="82d4f-110">Задает пространство имен XML, необходимое для привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="82d4f-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="82d4f-111">Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="82d4f-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="82d4f-112">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="82d4f-112">Parent element</span></span>

|     | <span data-ttu-id="82d4f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="82d4f-113">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="82d4f-114">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82d4f-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="82d4f-115">Дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="82d4f-115">Child element</span></span>

|     | <span data-ttu-id="82d4f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="82d4f-116">Description</span></span> |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | <span data-ttu-id="82d4f-117">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="82d4f-117">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="82d4f-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="82d4f-118">Remarks</span></span>

<span data-ttu-id="82d4f-119">[**\<linkedConfiguration>**](linkedconfiguration-element.md)Элемент упрощает управление сборками компонентов, позволяя файлам конфигурации приложения включать файлы конфигурации сборки в хорошо известные расположения, а не дублировать параметры конфигурации сборки.</span><span class="sxs-lookup"><span data-stu-id="82d4f-119">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="82d4f-120">**\<linkedConfiguration>** Элемент не поддерживается для приложений с параллельными манифестами Windows.</span><span class="sxs-lookup"><span data-stu-id="82d4f-120">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="82d4f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="82d4f-121">Example</span></span>

<span data-ttu-id="82d4f-122">В следующем примере показано, как включить файл конфигурации на локальный жесткий диск:</span><span class="sxs-lookup"><span data-stu-id="82d4f-122">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="82d4f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="82d4f-123">See also</span></span>

- [<span data-ttu-id="82d4f-124">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="82d4f-124">Configuration file schema for the .NET Framework</span></span>](index.md)
