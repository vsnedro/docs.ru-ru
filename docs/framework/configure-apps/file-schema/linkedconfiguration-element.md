---
title: <linkedConfiguration> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087965"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="cc159-102">Элемент \<linkedConfiguration></span><span class="sxs-lookup"><span data-stu-id="cc159-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="cc159-103">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="cc159-103">Specifies a configuration file to include.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a><span data-ttu-id="cc159-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc159-104">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="cc159-105">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cc159-105">Attribute</span></span>

|           | <span data-ttu-id="cc159-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cc159-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="cc159-107">**href**</span><span class="sxs-lookup"><span data-stu-id="cc159-107">**href**</span></span>  | <span data-ttu-id="cc159-108">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="cc159-108">Required attribute.</span></span><br><br><span data-ttu-id="cc159-109">URL-адрес файла конфигурации, который необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="cc159-109">The URL of the configuration file to include.</span></span> <span data-ttu-id="cc159-110">Единственным форматом, поддерживаемым для атрибута **href** , является `file://` .</span><span class="sxs-lookup"><span data-stu-id="cc159-110">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="cc159-111">Поддерживаются локальные файлы и файлы в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="cc159-111">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="cc159-112">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="cc159-112">Parent element</span></span>

|     | <span data-ttu-id="cc159-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cc159-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="cc159-114">**\<assemblyBinding>** Дерев</span><span class="sxs-lookup"><span data-stu-id="cc159-114">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="cc159-115">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cc159-115">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="cc159-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cc159-116">Child elements</span></span>

<span data-ttu-id="cc159-117">None</span><span class="sxs-lookup"><span data-stu-id="cc159-117">None</span></span>

## <a name="remarks"></a><span data-ttu-id="cc159-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="cc159-118">Remarks</span></span>

<span data-ttu-id="cc159-119">**\<linkedConfiguration>** Элемент упрощает обслуживание сборок компонентов.</span><span class="sxs-lookup"><span data-stu-id="cc159-119">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="cc159-120">Если одно или несколько приложений используют сборку с файлом конфигурации, находящимся в хорошо известном расположении, файлы конфигурации приложений, использующих эту сборку, могут использовать этот **\<linkedConfiguration>** элемент для включения файла конфигурации сборки, вместо того чтобы включать сведения о конфигурации напрямую.</span><span class="sxs-lookup"><span data-stu-id="cc159-120">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="cc159-121">При обслуживании сборки компонента обновление общего файла конфигурации предоставляет обновленные сведения о конфигурации всем приложениям, которые используют сборку.</span><span class="sxs-lookup"><span data-stu-id="cc159-121">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="cc159-122">**\<linkedConfiguration>** Элемент не поддерживается для приложений с параллельными манифестами Windows.</span><span class="sxs-lookup"><span data-stu-id="cc159-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="cc159-123">Следующие правила управляют использованием связанных файлов конфигурации:</span><span class="sxs-lookup"><span data-stu-id="cc159-123">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="cc159-124">Параметры в включаемых файлах конфигурации влияют только на политику привязки загрузчика и используются только загрузчиком.</span><span class="sxs-lookup"><span data-stu-id="cc159-124">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="cc159-125">Включаемые файлы конфигурации могут иметь параметры, отличные от политик привязки, но эти параметры не оказывают никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="cc159-125">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="cc159-126">Единственным форматом, поддерживаемым для `href` атрибута, является `file://` .</span><span class="sxs-lookup"><span data-stu-id="cc159-126">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="cc159-127">Поддерживаются локальные файлы и файлы в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="cc159-127">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="cc159-128">Ограничений на количество связанных конфигураций для каждого файла конфигурации не существует.</span><span class="sxs-lookup"><span data-stu-id="cc159-128">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="cc159-129">Все связанные файлы конфигурации объединяются в один файл, аналогично поведению `#include` директивы в C/C++.</span><span class="sxs-lookup"><span data-stu-id="cc159-129">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="cc159-130">**\<linkedConfiguration>** Элемент разрешен только в файлах конфигурации приложения. он игнорируется в *файле Machine. config*.</span><span class="sxs-lookup"><span data-stu-id="cc159-130">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="cc159-131">Обнаружены и завершаются циклические ссылки.</span><span class="sxs-lookup"><span data-stu-id="cc159-131">Circular references are detected and terminated.</span></span> <span data-ttu-id="cc159-132">То есть, если **\<linkedConfiguration>** элементы последовательности файлов конфигурации образуют цикл, цикл определяется и останавливается.</span><span class="sxs-lookup"><span data-stu-id="cc159-132">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="cc159-133">Пример</span><span class="sxs-lookup"><span data-stu-id="cc159-133">Example</span></span>

<span data-ttu-id="cc159-134">В следующем примере показано, как включить файл конфигурации с локального жесткого диска:</span><span class="sxs-lookup"><span data-stu-id="cc159-134">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="cc159-135">См. также</span><span class="sxs-lookup"><span data-stu-id="cc159-135">See also</span></span>

- [<span data-ttu-id="cc159-136">**\<assemblyBinding>** Дерев</span><span class="sxs-lookup"><span data-stu-id="cc159-136">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="cc159-137">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cc159-137">Configuration file schema for the .NET Framework</span></span>](index.md)
