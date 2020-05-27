---
title: Миграция из Newtonsoft.Json в System.Text.Json — .NET
author: ''
ms.author: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: ''
helpviewer_keywords: []
ms.openlocfilehash: fe370b34d311816a815f3b2d419751ac7871f013
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703578"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a><span data-ttu-id="4b77d-102">Миграция из Newtonsoft.Json в System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="4b77d-102">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>

<span data-ttu-id="4b77d-103">В этой статье описывается миграция из [Newtonsoft.Json](https://www.newtonsoft.com/json) в <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-103">This article shows how to migrate from [Newtonsoft.Json](https://www.newtonsoft.com/json) to <xref:System.Text.Json>.</span></span>

<span data-ttu-id="4b77d-104">Пространство имен `System.Text.Json` предоставляет функциональные возможности для сериализации в нотацию объектов JavaScript (JSON) и десериализации объектов из этой нотации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="4b77d-105">Библиотека `System.Text.Json` входит в состав общей платформы [.NET Core 3.0](https://aka.ms/netcore3download).</span><span class="sxs-lookup"><span data-stu-id="4b77d-105">The `System.Text.Json` library is included in the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span> <span data-ttu-id="4b77d-106">Для других целевых платформ установите пакет NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json).</span><span class="sxs-lookup"><span data-stu-id="4b77d-106">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="4b77d-107">Пакет поддерживает:</span><span class="sxs-lookup"><span data-stu-id="4b77d-107">The package supports:</span></span>

* <span data-ttu-id="4b77d-108">.NET Standard 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="4b77d-108">.NET Standard 2.0 and later versions</span></span>
* <span data-ttu-id="4b77d-109">.NET Framework 4.7.2 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="4b77d-109">.NET Framework 4.7.2 and later versions</span></span>
* <span data-ttu-id="4b77d-110">.NET Core 2.0, 2.1 и 2.2</span><span class="sxs-lookup"><span data-stu-id="4b77d-110">.NET Core 2.0, 2.1, and 2.2</span></span>

<span data-ttu-id="4b77d-111">`System.Text.Json` основное внимание уделяет требованиям, предъявляемым к производительности, безопасности и стандартам.</span><span class="sxs-lookup"><span data-stu-id="4b77d-111">`System.Text.Json` focuses primarily on performance, security, and standards compliance.</span></span> <span data-ttu-id="4b77d-112">У него есть некоторые ключевые отличия в поведении по умолчанию, и он не стремится к равенству функций с `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-112">It has some key differences in default behavior and doesn't aim to have feature parity with `Newtonsoft.Json`.</span></span> <span data-ttu-id="4b77d-113">В некоторых сценариях `System.Text.Json` не имеет встроенных функций, но существуют рекомендованные способы обойти проблему.</span><span class="sxs-lookup"><span data-stu-id="4b77d-113">For some scenarios, `System.Text.Json` has no built-in functionality, but there are recommended workarounds.</span></span> <span data-ttu-id="4b77d-114">В других сценариях обходные пути нецелесообразны.</span><span class="sxs-lookup"><span data-stu-id="4b77d-114">For other scenarios, workarounds are impractical.</span></span> <span data-ttu-id="4b77d-115">Если приложение зависит от отсутствующей функции, возможно, следует [сообщить о проблеме](https://github.com/dotnet/runtime/issues/new), чтобы узнать, можно ли добавить поддержку для вашего сценария.</span><span class="sxs-lookup"><span data-stu-id="4b77d-115">If your application depends on a missing feature, consider [filing an issue](https://github.com/dotnet/runtime/issues/new) to find out if support for your scenario can be added.</span></span>

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

<span data-ttu-id="4b77d-116">Большая часть этой статьи посвящена использованию API <xref:System.Text.Json.JsonSerializer>, но также содержит рекомендации по использованию <xref:System.Text.Json.JsonDocument> (который представляет модель DOM), <xref:System.Text.Json.Utf8JsonReader> и типов <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-116">Most of this article is about how to use the <xref:System.Text.Json.JsonSerializer> API, but it also includes guidance on how to use the <xref:System.Text.Json.JsonDocument> (which represents the Document Object Model or DOM), <xref:System.Text.Json.Utf8JsonReader>, and <xref:System.Text.Json.Utf8JsonWriter> types.</span></span>

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a><span data-ttu-id="4b77d-117">Таблица различий между Newtonsoft.Json и System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="4b77d-117">Table of differences between Newtonsoft.Json and System.Text.Json</span></span>

<span data-ttu-id="4b77d-118">В следующей таблице перечислены функции `Newtonsoft.Json` и эквиваленты `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-118">The following table lists `Newtonsoft.Json` features and `System.Text.Json` equivalents.</span></span> <span data-ttu-id="4b77d-119">Эквиваленты делятся на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="4b77d-119">The equivalents fall into the following categories:</span></span>

* <span data-ttu-id="4b77d-120">Поддерживается встроенными функциональными возможностями.</span><span class="sxs-lookup"><span data-stu-id="4b77d-120">Supported by built-in functionality.</span></span> <span data-ttu-id="4b77d-121">Для получения подобного поведения в `System.Text.Json` может потребоваться использование атрибута или глобального параметра.</span><span class="sxs-lookup"><span data-stu-id="4b77d-121">Getting similar behavior from `System.Text.Json` may require the use of an attribute or global option.</span></span>
* <span data-ttu-id="4b77d-122">Не поддерживается, существует обходной путь.</span><span class="sxs-lookup"><span data-stu-id="4b77d-122">Not supported, workaround is possible.</span></span> <span data-ttu-id="4b77d-123">В качестве обходных путей можно использовать [пользовательские преобразователи](system-text-json-converters-how-to.md), которые могут не обеспечивать полное равенство с функциями `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-123">The workarounds are [custom converters](system-text-json-converters-how-to.md), which may not provide complete parity with `Newtonsoft.Json` functionality.</span></span> <span data-ttu-id="4b77d-124">Для некоторых случаев приведены примеры кода.</span><span class="sxs-lookup"><span data-stu-id="4b77d-124">For some of these, sample code is provided as examples.</span></span> <span data-ttu-id="4b77d-125">Если вы используете эти функции `Newtonsoft.Json`, для миграции потребуется внести изменения в объектные модели .NET или другие части кода.</span><span class="sxs-lookup"><span data-stu-id="4b77d-125">If you rely on these `Newtonsoft.Json` features, migration will require modifications to your .NET object models or other code changes.</span></span>
* <span data-ttu-id="4b77d-126">Не поддерживается, обходной путь нецелесообразен или невозможен.</span><span class="sxs-lookup"><span data-stu-id="4b77d-126">Not supported, workaround is not practical or possible.</span></span> <span data-ttu-id="4b77d-127">Если вы используете эти функции `Newtonsoft.Json`, миграция будет невозможна без существенных изменений.</span><span class="sxs-lookup"><span data-stu-id="4b77d-127">If you rely on these `Newtonsoft.Json` features, migration will not be possible without significant changes.</span></span>

| <span data-ttu-id="4b77d-128">Функция Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="4b77d-128">Newtonsoft.Json feature</span></span>                               | <span data-ttu-id="4b77d-129">Эквивалент System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="4b77d-129">System.Text.Json equivalent</span></span> |
|---
<span data-ttu-id="4b77d-130">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-130">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-131">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-131">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-132">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-132">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-133">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-133">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-134">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-134">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-135">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-135">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-136">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-136">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-137">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-137">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-138">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-138">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-139">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-139">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-140">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-140">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-141">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-141">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-142">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-142">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-143">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-143">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-144">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-144">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-145">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-145">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-146">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-146">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-147">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-147">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-148">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-148">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-149">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-149">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-150">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-150">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-151">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-151">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-152">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-152">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-153">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-153">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-154">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-154">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-155">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-155">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-156">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-156">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-157">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-157">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-158">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-158">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-159">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-159">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-160">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-160">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-161">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-161">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-162">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-162">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-163">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-163">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-164">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-164">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-165">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-165">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-166">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-166">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-167">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-167">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-168">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-168">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-169">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-169">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-170">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-170">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-171">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-171">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-172">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-172">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-173">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-173">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-174">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-174">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-175">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-175">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-176">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-176">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-177">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-177">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-178">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-178">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-179">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-179">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-180">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-180">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-181">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-181">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-182">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-182">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-183">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-183">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-184">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-184">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-185">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-185">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-186">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-186">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-187">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-187">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-188">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-188">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-189">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-189">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-190">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-190">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-191">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-191">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-192">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-192">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-193">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-193">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-194">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-194">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-195">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-195">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-196">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-196">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-197">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-197">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-198">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-198">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-199">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-199">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-200">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-200">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-201">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-201">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-202">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-202">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-203">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-203">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-204">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-204">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="4b77d-205">----------------------------|--- title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-205">----------------------------|--- title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-206">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-206">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-207">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-207">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-208">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-208">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-209">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-209">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-210">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-210">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-211">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-211">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-212">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-212">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-213">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-213">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-214">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-214">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-215">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-215">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-216">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-216">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-217">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-217">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-218">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-218">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-219">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-219">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-220">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-220">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-221">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-221">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-222">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-222">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-223">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-223">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-224">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-224">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-225">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-225">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-226">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-226">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-227">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-227">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-228">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-228">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-229">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-229">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-230">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-230">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-231">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-231">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-232">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-232">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-233">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-233">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-234">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-234">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-235">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-235">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-236">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-236">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-237">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-237">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="4b77d-238">title: "Миграция из Newtonsoft.Json в System.Text.Json — .NET" author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="4b77d-238">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="4b77d-239">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="4b77d-239">'System.Text.Json'</span></span>
- <span data-ttu-id="4b77d-240">"Newtonsoft.Json" ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="4b77d-240">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="4b77d-241">---------------| | Десериализация без учета регистра по умолчанию           | ✔️ [Глобальный параметр PropertyNameCaseInsensitive](#case-insensitive-deserialization) | | Имена свойств в "верблюжьем" стиле                             | ✔️ [Глобальный параметр PropertyNamingPolicy](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | Минимальное экранирование символов                            | ✔️ [Строгое экранирование символов, возможность настройки](#minimal-character-escaping) | | Глобальный параметр `NullValueHandling.Ignore`             | ✔️ [Глобальный параметр IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) | | Разрешить комментарии                                        | ✔️ [Глобальный параметр ReadCommentHandling](#comments) | | Разрешить конечные запятые                                 | ✔️ [Глобальный параметр AllowTrailingCommas](#trailing-commas) | | Регистрация пользовательского преобразователя                         | ✔️ [Различие порядка приоритета](#converter-registration-precedence) | | Отсутствие максимальной глубины по умолчанию                           | ✔️ [Максимальная глубина по умолчанию 64, возможность настройки](#maximum-depth) | | Поддержка широкого диапазона типов                    | ⚠️ [Некоторые типы требуют пользовательских преобразователей](#types-without-built-in-support) | | Десериализация строк в виде чисел                        | ⚠️ [Не поддерживается, обходное решение, пример](#quoted-numbers) | | Десериализация `Dictionary` с ключом, не являющимся строкой          | ⚠️ [Не поддерживается, обходное решение, пример](#dictionary-with-non-string-key) | | Полиморфная сериализация                             | ⚠️ [Не поддерживается, обходное решение, пример](#polymorphic-serialization) | | Полиморфная десериализация                           | ⚠️ [Не поддерживается, обходное решение, пример](#polymorphic-deserialization) | | Десериализация выводимого типа в свойства `object`       | ⚠️ [Не поддерживается, обходное решение, пример](#deserialization-of-object-properties) | | Десериализация литерала JSON `null` в типы значений, не допускающие значения NULL | ⚠️ [Не поддерживается, обходное решение, пример](#deserialize-null-to-non-nullable-type) | | Десериализация в неизменяемые классы и структуры          | ⚠️ [Не поддерживается, обходное решение, пример](#deserialize-to-immutable-classes-and-structs) | | Атрибут `[JsonConstructor]`                          | ⚠️ [Не поддерживается, обходное решение, пример](#specify-constructor-to-use) | | Параметр `Required` для атрибута `[JsonProperty]`         | ⚠️ [Не поддерживается, обходное решение, пример](#required-properties) | | Параметр `NullValueHandling` для атрибута `[JsonProperty]` | ⚠️ [Не поддерживается, обходное решение, пример](#conditionally-ignore-a-property)  | | Параметр `DefaultValueHandling` для атрибута `[JsonProperty]` | ⚠️ [Не поддерживается, обходное решение, пример](#conditionally-ignore-a-property)  | | Глобальный параметр `DefaultValueHandling`                  | ⚠️ [Не поддерживается, обходное решение, пример](#conditionally-ignore-a-property) | | `DefaultContractResolver` для исключения свойств       | ⚠️ [Не поддерживается, обходное решение, пример](#conditionally-ignore-a-property) | | Параметры `DateTimeZoneHandling`, `DateFormatString`   | ⚠️ [Не поддерживается, обходное решение, пример](#specify-date-format) | | Обратные вызовы                                             | ⚠️ [Не поддерживается, обходное решение, пример](#callbacks) | | Поддержка открытых и закрытых полей              | ⚠️ [Не поддерживается, обходное решение](#public-and-non-public-fields) | | Поддержка внутренних и частных методов задания и получения | ⚠️ [Не поддерживается, обходное решение](#internal-and-private-property-setters-and-getters) | | Метод `JsonConvert.PopulateObject`                    | ⚠️ [Не поддерживается, обходное решение](#populate-existing-objects) | | Глобальный параметр `ObjectCreationHandling`               | ⚠️ [Не поддерживается, обходное решение](#reuse-rather-than-replace-properties) | | Добавление в коллекции без методов задания                    | ⚠️ [Не поддерживается, обходное решение](#add-to-collections-without-setters) | | Глобальный параметр `PreserveReferencesHandling`           | ❌ [Не поддерживается](#preserve-object-references-and-handle-loops) | | Глобальный параметр `ReferenceLoopHandling`                | ❌ [Не поддерживается](#preserve-object-references-and-handle-loops) | | Поддержка атрибутов `System.Runtime.Serialization` | ❌ [Не поддерживается](#systemruntimeserialization-attributes) | | Глобальный параметр `MissingMemberHandling`                 | ❌ [Не поддерживается](#missingmemberhandling) | | Разрешить имена свойств без кавычек                   | ❌ [Не поддерживается](#json-strings-property-names-and-string-values) | | Разрешить одинарные кавычки для строковых значений              | ❌ [Не поддерживается](#json-strings-property-names-and-string-values) | | Разрешить нестроковые значения JSON для строковых свойств    | ❌ [Не поддерживается](#non-string-values-for-string-properties) |</span><span class="sxs-lookup"><span data-stu-id="4b77d-241">---------------| | Case-insensitive deserialization by default           | ✔️ [PropertyNameCaseInsensitive global setting](#case-insensitive-deserialization) | | Camel-case property names                             | ✔️ [PropertyNamingPolicy global setting](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | Minimal character escaping                            | ✔️ [Strict character escaping, configurable](#minimal-character-escaping) | | `NullValueHandling.Ignore` global setting             | ✔️ [IgnoreNullValues global option](system-text-json-how-to.md#exclude-all-null-value-properties) | | Allow comments                                        | ✔️ [ReadCommentHandling global setting](#comments) | | Allow trailing commas                                 | ✔️ [AllowTrailingCommas global setting](#trailing-commas) | | Custom converter registration                         | ✔️ [Order of precedence differs](#converter-registration-precedence) | | No maximum depth by default                           | ✔️ [Default maximum depth 64, configurable](#maximum-depth) | | Support for a broad range of types                    | ⚠️ [Some types require custom converters](#types-without-built-in-support) | | Deserialize strings as numbers                        | ⚠️ [Not supported, workaround, sample](#quoted-numbers) | | Deserialize `Dictionary` with non-string key          | ⚠️ [Not supported, workaround, sample](#dictionary-with-non-string-key) | | Polymorphic serialization                             | ⚠️ [Not supported, workaround, sample](#polymorphic-serialization) | | Polymorphic deserialization                           | ⚠️ [Not supported, workaround, sample](#polymorphic-deserialization) | | Deserialize inferred type to `object` properties      | ⚠️ [Not supported, workaround, sample](#deserialization-of-object-properties) | | Deserialize JSON `null` literal to non-nullable value types | ⚠️ [Not supported, workaround, sample](#deserialize-null-to-non-nullable-type) | | Deserialize to immutable classes and structs          | ⚠️ [Not supported, workaround, sample](#deserialize-to-immutable-classes-and-structs) | | `[JsonConstructor]` attribute                         | ⚠️ [Not supported, workaround, sample](#specify-constructor-to-use) | | `Required` setting on `[JsonProperty]` attribute        | ⚠️ [Not supported, workaround, sample](#required-properties) | | `NullValueHandling` setting on `[JsonProperty]` attribute | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property)  | | `DefaultValueHandling` setting on `[JsonProperty]` attribute | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property)  | | `DefaultValueHandling` global setting                 | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property) | | `DefaultContractResolver` to exclude properties       | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property) | | `DateTimeZoneHandling`, `DateFormatString` settings   | ⚠️ [Not supported, workaround, sample](#specify-date-format) | | Callbacks                                             | ⚠️ [Not supported, workaround, sample](#callbacks) | | Support for public and non-public fields              | ⚠️ [Not supported, workaround](#public-and-non-public-fields) | | Support for internal and private property setters and getters | ⚠️ [Not supported, workaround](#internal-and-private-property-setters-and-getters) | | `JsonConvert.PopulateObject` method                   | ⚠️ [Not supported, workaround](#populate-existing-objects) | | `ObjectCreationHandling` global setting               | ⚠️ [Not supported, workaround](#reuse-rather-than-replace-properties) | | Add to collections without setters                    | ⚠️ [Not supported, workaround](#add-to-collections-without-setters) | | `PreserveReferencesHandling` global setting           | ❌ [Not supported](#preserve-object-references-and-handle-loops) | | `ReferenceLoopHandling` global setting                | ❌ [Not supported](#preserve-object-references-and-handle-loops) | | Support for `System.Runtime.Serialization` attributes | ❌ [Not supported](#systemruntimeserialization-attributes) | | `MissingMemberHandling` global setting                | ❌ [Not supported](#missingmemberhandling) | | Allow property names without quotes                   | ❌ [Not supported](#json-strings-property-names-and-string-values) | | Allow single quotes around string values              | ❌ [Not supported](#json-strings-property-names-and-string-values) | | Allow non-string JSON values for string properties    | ❌ [Not supported](#non-string-values-for-string-properties) |</span></span>

<span data-ttu-id="4b77d-242">Это неполный список функций `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-242">This is not an exhaustive list of `Newtonsoft.Json` features.</span></span> <span data-ttu-id="4b77d-243">В список входят многие сценарии, которые были запрошены в [проблемах GitHub](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) или записях [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json).</span><span class="sxs-lookup"><span data-stu-id="4b77d-243">The list includes many of the scenarios that have been requested in [GitHub issues](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) or [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) posts.</span></span> <span data-ttu-id="4b77d-244">Если вы реализуете обходной путь для одного из перечисленных здесь сценариев, для которого в настоящее время нет примера кода, и если вы хотите поделиться своим решением, нажмите **Эта страница** в разделе **Отзывы** (в нижней части этой страницы).</span><span class="sxs-lookup"><span data-stu-id="4b77d-244">If you implement a workaround for one of the scenarios listed here that doesn't currently have sample code, and if you want to share your solution, select **This page** in the **Feedback** section at the bottom of this page.</span></span> <span data-ttu-id="4b77d-245">Это позволит создать проблему в репозитории GitHub в этой документации и указать ее в разделе **Отзывы** на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4b77d-245">That creates an issue in this documentation's GitHub repo and lists it in the **Feedback** section on this page too.</span></span>

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a><span data-ttu-id="4b77d-246">Различия в поведении JsonSerializer по умолчанию по сравнению с Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="4b77d-246">Differences in default JsonSerializer behavior compared to Newtonsoft.Json</span></span>

<span data-ttu-id="4b77d-247"><xref:System.Text.Json> по умолчанию является строгим и избегает двусмысленностей со стороны вызывающего объекта, подчеркивая детерминированное поведение.</span><span class="sxs-lookup"><span data-stu-id="4b77d-247"><xref:System.Text.Json> is strict by default and avoids any guessing or interpretation on the caller's behalf, emphasizing deterministic behavior.</span></span> <span data-ttu-id="4b77d-248">Библиотека преднамеренно разработана таким образом для повышения производительности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b77d-248">The library is intentionally designed this way for performance and security.</span></span> <span data-ttu-id="4b77d-249">`Newtonsoft.Json` по умолчанию является гибким.</span><span class="sxs-lookup"><span data-stu-id="4b77d-249">`Newtonsoft.Json` is flexible by default.</span></span> <span data-ttu-id="4b77d-250">Это фундаментальное различие в проектировании обуславливает многие из следующих различий в поведении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b77d-250">This fundamental difference in design is behind many of the following specific differences in default behavior.</span></span>

### <a name="case-insensitive-deserialization"></a><span data-ttu-id="4b77d-251">Десериализация без учета регистра</span><span class="sxs-lookup"><span data-stu-id="4b77d-251">Case-insensitive deserialization</span></span>

<span data-ttu-id="4b77d-252">Во время десериализации `Newtonsoft.Json` выполняет сопоставление имени свойства без учета регистра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b77d-252">During deserialization, `Newtonsoft.Json` does case-insensitive property name matching by default.</span></span> <span data-ttu-id="4b77d-253"><xref:System.Text.Json> по умолчанию учитывает регистр, что обеспечивает более высокую производительность, так как соответствие является точным.</span><span class="sxs-lookup"><span data-stu-id="4b77d-253">The <xref:System.Text.Json> default is case-sensitive, which gives better performance since it's doing an exact match.</span></span> <span data-ttu-id="4b77d-254">Сведения о том, как выполнять сопоставление без учета регистра, см. в разделе [Сопоставление свойств без учета регистра](system-text-json-how-to.md#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="4b77d-254">For information about how to do case-insensitive matching, see [Case-insensitive property matching](system-text-json-how-to.md#case-insensitive-property-matching).</span></span>

<span data-ttu-id="4b77d-255">Если вы используете `System.Text.Json` косвенно с помощью ASP.NET Core, вам не нужно ничего делать для получения поведения, аналогичного `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-255">If you're using `System.Text.Json` indirectly by using ASP.NET Core, you don't need to do anything to get behavior like `Newtonsoft.Json`.</span></span> <span data-ttu-id="4b77d-256">ASP.NET Core задает параметры для [имен свойств в "верблюжьем" стиле](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) и сопоставления без учета регистра при использовании `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-256">ASP.NET Core specifies the settings for [camel-casing property names](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) and case-insensitive matching when it uses `System.Text.Json`.</span></span>

### <a name="minimal-character-escaping"></a><span data-ttu-id="4b77d-257">Минимальное экранирование символов</span><span class="sxs-lookup"><span data-stu-id="4b77d-257">Minimal character escaping</span></span>

<span data-ttu-id="4b77d-258">Во время сериализации `Newtonsoft.Json` обеспечивает относительную свободу, разрешая символы без экранирования.</span><span class="sxs-lookup"><span data-stu-id="4b77d-258">During serialization, `Newtonsoft.Json` is relatively permissive about letting characters through without escaping them.</span></span> <span data-ttu-id="4b77d-259">То есть он не заменяет их на `\uxxxx`, где `xxxx` является кодовой точкой символа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-259">That is, it doesn't replace them with `\uxxxx` where `xxxx` is the character's code point.</span></span> <span data-ttu-id="4b77d-260">Когда он использует экранирование, он выдает `\` перед символом (например, `"` преобразуется в `\"`).</span><span class="sxs-lookup"><span data-stu-id="4b77d-260">Where it does escape them, it does so by emitting a `\` before the character (for example, `"` becomes `\"`).</span></span> <span data-ttu-id="4b77d-261"><xref:System.Text.Json> по умолчанию экранирует больше символов, чтобы обеспечить глубокую защиту от межсайтового скриптинга (XSS) или атак с раскрытием информации и делает это с помощью последовательности из шести символов.</span><span class="sxs-lookup"><span data-stu-id="4b77d-261"><xref:System.Text.Json> escapes more characters by default to provide defense-in-depth protections against cross-site scripting (XSS) or information-disclosure attacks and does so by using the six-character sequence.</span></span> <span data-ttu-id="4b77d-262">`System.Text.Json` экранирует все символы, отличные от ASCII, по умолчанию, поэтому вам не нужно ничего делать, если вы используете `StringEscapeHandling.EscapeNonAscii` в `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-262">`System.Text.Json` escapes all non-ASCII characters by default, so you don't need to do anything if you're using `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json`.</span></span> <span data-ttu-id="4b77d-263">`System.Text.Json` также по умолчанию экранирует символы, учитывающие HTML.</span><span class="sxs-lookup"><span data-stu-id="4b77d-263">`System.Text.Json` also escapes HTML-sensitive characters, by default.</span></span> <span data-ttu-id="4b77d-264">Сведения о том, как переопределить поведение `System.Text.Json` по умолчанию, см. в разделе [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).</span><span class="sxs-lookup"><span data-stu-id="4b77d-264">For information about how to override the default `System.Text.Json` behavior, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="comments"></a><span data-ttu-id="4b77d-265">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4b77d-265">Comments</span></span>

<span data-ttu-id="4b77d-266">Во время десериализации `Newtonsoft.Json` по умолчанию игнорирует комментарии в JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-266">During deserialization, `Newtonsoft.Json` ignores comments in the JSON by default.</span></span> <span data-ttu-id="4b77d-267"><xref:System.Text.Json> по умолчанию выдает исключения для комментариев, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не включает их.</span><span class="sxs-lookup"><span data-stu-id="4b77d-267">The <xref:System.Text.Json> default is to throw exceptions for comments because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't include them.</span></span> <span data-ttu-id="4b77d-268">Сведения о том, как разрешить комментарии, см. в разделе [Возможность комментариев и конечных запятых](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="4b77d-268">For information about how to allow comments, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span>

### <a name="trailing-commas"></a><span data-ttu-id="4b77d-269">Конечные запятые</span><span class="sxs-lookup"><span data-stu-id="4b77d-269">Trailing commas</span></span>

<span data-ttu-id="4b77d-270">Во время десериализации `Newtonsoft.Json` по умолчанию игнорирует конечные запятые.</span><span class="sxs-lookup"><span data-stu-id="4b77d-270">During deserialization, `Newtonsoft.Json` ignores trailing commas by default.</span></span> <span data-ttu-id="4b77d-271">Он также игнорирует несколько конечных запятых (например, `[{"Color":"Red"},{"Color":"Green"},,]`).</span><span class="sxs-lookup"><span data-stu-id="4b77d-271">It also ignores multiple trailing commas (for example, `[{"Color":"Red"},{"Color":"Green"},,]`).</span></span> <span data-ttu-id="4b77d-272"><xref:System.Text.Json> по умолчанию выдает исключения для конечных запятых, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не разрешает их.</span><span class="sxs-lookup"><span data-stu-id="4b77d-272">The <xref:System.Text.Json> default is to throw exceptions for trailing commas because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span> <span data-ttu-id="4b77d-273">Сведения о том, как заставить `System.Text.Json` их принять, см. в разделе [Возможность комментариев и конечных запятых](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="4b77d-273">For information about how to make `System.Text.Json` accept them, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span> <span data-ttu-id="4b77d-274">Невозможно разрешить несколько конечных запятых.</span><span class="sxs-lookup"><span data-stu-id="4b77d-274">There's no way to allow multiple trailing commas.</span></span>

### <a name="converter-registration-precedence"></a><span data-ttu-id="4b77d-275">Очередность регистрации преобразователей</span><span class="sxs-lookup"><span data-stu-id="4b77d-275">Converter registration precedence</span></span>

<span data-ttu-id="4b77d-276">Очередность регистрации `Newtonsoft.Json` для пользовательских преобразователей выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4b77d-276">The `Newtonsoft.Json` registration precedence for custom converters is as follows:</span></span>

* <span data-ttu-id="4b77d-277">Атрибут для свойства</span><span class="sxs-lookup"><span data-stu-id="4b77d-277">Attribute on property</span></span>
* <span data-ttu-id="4b77d-278">Атрибут для типа</span><span class="sxs-lookup"><span data-stu-id="4b77d-278">Attribute on type</span></span>
* <span data-ttu-id="4b77d-279">Коллекция [преобразователей](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)</span><span class="sxs-lookup"><span data-stu-id="4b77d-279">[Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) collection</span></span>

<span data-ttu-id="4b77d-280">Этот порядок означает, что пользовательский преобразователь в коллекции `Converters` переопределяется преобразователем, зарегистрированным путем применения атрибута на уровне типа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-280">This order means that a custom converter in the `Converters` collection is overridden by a converter that is registered by applying an attribute at the type level.</span></span> <span data-ttu-id="4b77d-281">Обе эти регистрации переопределяются атрибутом на уровне свойства.</span><span class="sxs-lookup"><span data-stu-id="4b77d-281">Both of those registrations are overridden by an attribute at the property level.</span></span>

<span data-ttu-id="4b77d-282">Очередность регистрации <xref:System.Text.Json> для пользовательских преобразователей выглядит иначе:</span><span class="sxs-lookup"><span data-stu-id="4b77d-282">The <xref:System.Text.Json> registration precedence for custom converters is different:</span></span>

* <span data-ttu-id="4b77d-283">Атрибут для свойства</span><span class="sxs-lookup"><span data-stu-id="4b77d-283">Attribute on property</span></span>
* <span data-ttu-id="4b77d-284">Коллекция <xref:System.Text.Json.JsonSerializerOptions.Converters></span><span class="sxs-lookup"><span data-stu-id="4b77d-284"><xref:System.Text.Json.JsonSerializerOptions.Converters> collection</span></span>
* <span data-ttu-id="4b77d-285">Атрибут для типа</span><span class="sxs-lookup"><span data-stu-id="4b77d-285">Attribute on type</span></span>

<span data-ttu-id="4b77d-286">Разница заключается в том, что пользовательский преобразователь в коллекции `Converters` переопределяет атрибут на уровне типа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-286">The difference here is that a custom converter in the `Converters` collection overrides an attribute at the type level.</span></span> <span data-ttu-id="4b77d-287">Цель этой очередности заключается в том, чтобы изменения во время выполнения переопределяли варианты во время разработки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-287">The intention behind this order of precedence is to make run-time changes override design-time choices.</span></span> <span data-ttu-id="4b77d-288">Изменить очередность невозможно.</span><span class="sxs-lookup"><span data-stu-id="4b77d-288">There's no way to change the precedence.</span></span>

<span data-ttu-id="4b77d-289">Дополнительные сведения о регистрации пользовательских преобразователей см. в разделе [Регистрация пользовательского преобразователя](system-text-json-converters-how-to.md#register-a-custom-converter).</span><span class="sxs-lookup"><span data-stu-id="4b77d-289">For more information about custom converter registration, see [Register a custom converter](system-text-json-converters-how-to.md#register-a-custom-converter).</span></span>

### <a name="maximum-depth"></a><span data-ttu-id="4b77d-290">Максимальная глубина</span><span class="sxs-lookup"><span data-stu-id="4b77d-290">Maximum depth</span></span>

<span data-ttu-id="4b77d-291">`Newtonsoft.Json` по умолчанию не имеет максимального предела глубины.</span><span class="sxs-lookup"><span data-stu-id="4b77d-291">`Newtonsoft.Json` doesn't have a maximum depth limit by default.</span></span> <span data-ttu-id="4b77d-292">Для <xref:System.Text.Json> существует ограничение по умолчанию 64, которое можно настроить, задав <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-292">For <xref:System.Text.Json> there's a default limit  of 64, and it's configurable by setting <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.</span></span>

### <a name="json-strings-property-names-and-string-values"></a><span data-ttu-id="4b77d-293">Строки JSON (имена свойств и строковые значения)</span><span class="sxs-lookup"><span data-stu-id="4b77d-293">JSON strings (property names and string values)</span></span>

<span data-ttu-id="4b77d-294">Во время десериализации `Newtonsoft.Json` принимает имена свойств, заключенные в двойные кавычки, одинарные кавычки или без кавычек.</span><span class="sxs-lookup"><span data-stu-id="4b77d-294">During deserialization, `Newtonsoft.Json` accepts property names surrounded by double quotes, single quotes, or without quotes.</span></span> <span data-ttu-id="4b77d-295">Он принимает строковые значения, заключенные в двойные кавычки или одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-295">It accepts string values surrounded by double quotes or single quotes.</span></span> <span data-ttu-id="4b77d-296">Например, `Newtonsoft.Json` принимает следующий код JSON:</span><span class="sxs-lookup"><span data-stu-id="4b77d-296">For example, `Newtonsoft.Json` accepts the following JSON:</span></span>

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

<span data-ttu-id="4b77d-297">`System.Text.Json` принимает имена свойств и строковые значения только в двойных кавычках, так как этот формат требуется спецификацией [RFC 8259](https://tools.ietf.org/html/rfc8259) и является единственным форматом, который считается допустимым JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-297">`System.Text.Json` only accepts property names and string values in double quotes because that format is required by the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification and is the only format considered valid JSON.</span></span>

<span data-ttu-id="4b77d-298">Значение, заключенное в одинарные кавычки, приводит к исключению [JsonException](xref:System.Text.Json.JsonException) со следующим сообщением:</span><span class="sxs-lookup"><span data-stu-id="4b77d-298">A value enclosed in single quotes results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a><span data-ttu-id="4b77d-299">Нестроковые значения для строковых свойств</span><span class="sxs-lookup"><span data-stu-id="4b77d-299">Non-string values for string properties</span></span>

<span data-ttu-id="4b77d-300">`Newtonsoft.Json` принимает нестроковые значения, например числа или литералы `true` и `false`, для десериализации в свойства строкового типа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-300">`Newtonsoft.Json` accepts non-string values, such as a number or the literals `true` and `false`, for deserialization to properties of type string.</span></span> <span data-ttu-id="4b77d-301">Ниже приведен пример JSON, который `Newtonsoft.Json` успешно десериализует в следующий класс:</span><span class="sxs-lookup"><span data-stu-id="4b77d-301">Here's an example of JSON that `Newtonsoft.Json` successfully deserializes to the following class:</span></span>

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

<span data-ttu-id="4b77d-302">`System.Text.Json` не выполняет десериализацию нестроковых значений в строковые свойства.</span><span class="sxs-lookup"><span data-stu-id="4b77d-302">`System.Text.Json` doesn't deserialize non-string values into string properties.</span></span> <span data-ttu-id="4b77d-303">Нестроковое значение, полученное для строкового поля, приводит к исключению [JsonException](xref:System.Text.Json.JsonException) со следующим сообщением:</span><span class="sxs-lookup"><span data-stu-id="4b77d-303">A non-string value received for a string field results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a><span data-ttu-id="4b77d-304">Сценарии с использованием JsonSerializer, для которых требуются обходные пути</span><span class="sxs-lookup"><span data-stu-id="4b77d-304">Scenarios using JsonSerializer that require workarounds</span></span>

<span data-ttu-id="4b77d-305">Следующие сценарии не поддерживаются встроенными функциями, но возможны обходные пути.</span><span class="sxs-lookup"><span data-stu-id="4b77d-305">The following scenarios aren't supported by built-in functionality, but workarounds are possible.</span></span> <span data-ttu-id="4b77d-306">В качестве обходных путей можно использовать [пользовательские преобразователи](system-text-json-converters-how-to.md), которые могут не обеспечивать полное равенство с функциями `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-306">The workarounds are [custom converters](system-text-json-converters-how-to.md), which may not provide complete parity with `Newtonsoft.Json` functionality.</span></span> <span data-ttu-id="4b77d-307">Для некоторых случаев приведены примеры кода.</span><span class="sxs-lookup"><span data-stu-id="4b77d-307">For some of these, sample code is provided as examples.</span></span> <span data-ttu-id="4b77d-308">Если вы используете эти функции `Newtonsoft.Json`, для миграции потребуется внести изменения в объектные модели .NET или другие части кода.</span><span class="sxs-lookup"><span data-stu-id="4b77d-308">If you rely on these `Newtonsoft.Json` features, migration will require modifications to your .NET object models or other code changes.</span></span>

### <a name="types-without-built-in-support"></a><span data-ttu-id="4b77d-309">Типы без встроенной поддержки</span><span class="sxs-lookup"><span data-stu-id="4b77d-309">Types without built-in support</span></span>

<span data-ttu-id="4b77d-310"><xref:System.Text.Json> не предоставляет встроенную поддержку для следующих типов:</span><span class="sxs-lookup"><span data-stu-id="4b77d-310"><xref:System.Text.Json> doesn't provide built-in support for the following types:</span></span>

* <span data-ttu-id="4b77d-311"><xref:System.Data.DataTable> и связанные типы</span><span class="sxs-lookup"><span data-stu-id="4b77d-311"><xref:System.Data.DataTable> and related types</span></span>
* <span data-ttu-id="4b77d-312">Типы F#, такие как [различаемые объединения](../../fsharp/language-reference/discriminated-unions.md), [типы записей](../../fsharp/language-reference/records.md) и [типы анонимных записей](../../fsharp/language-reference/anonymous-records.md).</span><span class="sxs-lookup"><span data-stu-id="4b77d-312">F# types, such as [discriminated unions](../../fsharp/language-reference/discriminated-unions.md), [record types](../../fsharp/language-reference/records.md), and [anonymous record types](../../fsharp/language-reference/anonymous-records.md).</span></span>
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <span data-ttu-id="4b77d-313"><xref:System.ValueTuple> и связанные с ним универсальные типы</span><span class="sxs-lookup"><span data-stu-id="4b77d-313"><xref:System.ValueTuple> and its associated generic types</span></span>

<span data-ttu-id="4b77d-314">Пользовательские преобразователи можно реализовать для типов, у которых нет встроенной поддержки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-314">Custom converters can be implemented for types that don't have built-in support.</span></span>

### <a name="quoted-numbers"></a><span data-ttu-id="4b77d-315">Заключенные в кавычки числа</span><span class="sxs-lookup"><span data-stu-id="4b77d-315">Quoted numbers</span></span>

<span data-ttu-id="4b77d-316">`Newtonsoft.Json` может сериализовать или десериализовать числа, представленные строками JSON (заключенные в кавычки).</span><span class="sxs-lookup"><span data-stu-id="4b77d-316">`Newtonsoft.Json` can serialize or deserialize numbers represented by JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="4b77d-317">Например, он может принимать `{"DegreesCelsius":"23"}` вместо `{"DegreesCelsius":23}`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-317">For example, it can accept: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="4b77d-318">Чтобы включить это поведение в <xref:System.Text.Json>, реализуйте пользовательский преобразователь, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4b77d-318">To enable that behavior in <xref:System.Text.Json>, implement a custom converter like the following example.</span></span> <span data-ttu-id="4b77d-319">Преобразователь обрабатывает свойства, определенные как `long`:</span><span class="sxs-lookup"><span data-stu-id="4b77d-319">The converter handles properties defined as `long`:</span></span>

* <span data-ttu-id="4b77d-320">Он сериализует их как строки JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-320">It serializes them as JSON strings.</span></span>
* <span data-ttu-id="4b77d-321">Он принимает числа JSON и числа в кавычках при десериализации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-321">It accepts JSON numbers and numbers within quotes while deserializing.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/LongToStringConverter.cs)]

<span data-ttu-id="4b77d-322">Зарегистрируйте этот пользовательский преобразователь, [используя атрибут](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) для отдельных свойств `long` или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-322">Register this custom converter by [using an attribute](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) on individual `long` properties or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

### <a name="dictionary-with-non-string-key"></a><span data-ttu-id="4b77d-323">Словарь с ключом, не являющимся строкой</span><span class="sxs-lookup"><span data-stu-id="4b77d-323">Dictionary with non-string key</span></span>

<span data-ttu-id="4b77d-324">`Newtonsoft.Json` поддерживает коллекции типа `Dictionary<TKey, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-324">`Newtonsoft.Json` supports collections of type `Dictionary<TKey, TValue>`.</span></span> <span data-ttu-id="4b77d-325">Встроенная поддержка коллекций словарей в <xref:System.Text.Json> ограничена `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-325">The built-in support for dictionary collections in <xref:System.Text.Json> is limited to `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="4b77d-326">То есть ключ должен быть строкой.</span><span class="sxs-lookup"><span data-stu-id="4b77d-326">That is, the key must be a string.</span></span>

<span data-ttu-id="4b77d-327">Для поддержки словаря с целым числом или другим типом в качестве ключа создайте преобразователь, аналогичный примеру в разделе [Как писать пользовательские преобразователи](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="4b77d-327">To support a dictionary with an integer or some other type as the key, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).</span></span>

### <a name="polymorphic-serialization"></a><span data-ttu-id="4b77d-328">Полиморфная сериализация</span><span class="sxs-lookup"><span data-stu-id="4b77d-328">Polymorphic serialization</span></span>

<span data-ttu-id="4b77d-329">`Newtonsoft.Json` автоматически выполняет полиморфную сериализацию.</span><span class="sxs-lookup"><span data-stu-id="4b77d-329">`Newtonsoft.Json` automatically does polymorphic serialization.</span></span> <span data-ttu-id="4b77d-330">Сведения о возможностях ограниченной полиморфной сериализации в <xref:System.Text.Json> см. в разделе [Сериализация свойств производных классов](system-text-json-how-to.md#serialize-properties-of-derived-classes).</span><span class="sxs-lookup"><span data-stu-id="4b77d-330">For information about the limited polymorphic serialization capabilities of <xref:System.Text.Json>, see [Serialize properties of derived classes](system-text-json-how-to.md#serialize-properties-of-derived-classes).</span></span>

<span data-ttu-id="4b77d-331">Описанный обходной путь состоит в определении свойств, которые могут содержать производные классы в качестве типа `object`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-331">The workaround described there is to define properties that may contain derived classes as type `object`.</span></span> <span data-ttu-id="4b77d-332">Если это невозможно, можно создать преобразователь с методом `Write` для всей иерархии типов наследования, как в примере в разделе [Написание пользовательских преобразователей](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4b77d-332">If that isn't possible, another option is to create a converter with a `Write` method for the whole inheritance type hierarchy like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="polymorphic-deserialization"></a><span data-ttu-id="4b77d-333">Полиморфная десериализация</span><span class="sxs-lookup"><span data-stu-id="4b77d-333">Polymorphic deserialization</span></span>

<span data-ttu-id="4b77d-334">`Newtonsoft.Json` имеет параметр `TypeNameHandling`, который добавляет метаданные имени типа в JSON во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-334">`Newtonsoft.Json` has a `TypeNameHandling` setting that adds type name metadata to the JSON while serializing.</span></span> <span data-ttu-id="4b77d-335">Он использует метаданные во время десериализации для выполнения полиморфной десериализации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-335">It uses the metadata while deserializing to do polymorphic deserialization.</span></span> <span data-ttu-id="4b77d-336"><xref:System.Text.Json> может ограниченно выполнять [полиморфную сериализацию](system-text-json-how-to.md#serialize-properties-of-derived-classes), но не полиморфную десериализацию.</span><span class="sxs-lookup"><span data-stu-id="4b77d-336"><xref:System.Text.Json> can do a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but not polymorphic deserialization.</span></span>

<span data-ttu-id="4b77d-337">Чтобы обеспечить поддержку полиморфной десериализации, создайте преобразователь, как в примере в разделе [Написание пользовательских преобразователей](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4b77d-337">To support polymorphic deserialization, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="deserialization-of-object-properties"></a><span data-ttu-id="4b77d-338">Десериализация свойств объекта</span><span class="sxs-lookup"><span data-stu-id="4b77d-338">Deserialization of object properties</span></span>

<span data-ttu-id="4b77d-339">Когда `Newtonsoft.Json` выполняет десериализацию в <xref:System.Object>, он:</span><span class="sxs-lookup"><span data-stu-id="4b77d-339">When `Newtonsoft.Json` deserializes to <xref:System.Object>, it:</span></span>

* <span data-ttu-id="4b77d-340">Выводит типы примитивных значений в полезных данных JSON (кроме `null`) и возвращает хранимые `string`, `long`, `double`, `boolean` или `DateTime` в виде упакованного объекта.</span><span class="sxs-lookup"><span data-stu-id="4b77d-340">Infers the type of primitive values in the JSON payload (other than `null`) and returns the stored `string`, `long`, `double`, `boolean`, or `DateTime` as a boxed object.</span></span> <span data-ttu-id="4b77d-341">*Примитивные значения* — это отдельные значения JSON, такие как число JSON, строка, `true`, `false` или `null`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-341">*Primitive values* are single JSON values such as a JSON number, string, `true`, `false`, or `null`.</span></span>
* <span data-ttu-id="4b77d-342">Возвращает `JObject` или `JArray` для сложных значений в полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-342">Returns a `JObject` or `JArray` for complex values in the JSON payload.</span></span> <span data-ttu-id="4b77d-343">*Сложные значения* являются коллекциями пар "ключ-значение" JSON в фигурных скобках (`{}`) или списками значений в квадратных скобках (`[]`).</span><span class="sxs-lookup"><span data-stu-id="4b77d-343">*Complex values* are collections of JSON key-value pairs within braces (`{}`) or lists of values within brackets (`[]`).</span></span> <span data-ttu-id="4b77d-344">Свойства и значения в фигурных или квадратных скобках могут иметь дополнительные свойства или значения.</span><span class="sxs-lookup"><span data-stu-id="4b77d-344">The properties and values within the braces or brackets can have additional properties or values.</span></span>
* <span data-ttu-id="4b77d-345">Возвращает пустую ссылку, если полезная нагрузка содержит литерал `null` JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-345">Returns a null reference when the payload has the `null` JSON literal.</span></span>

<span data-ttu-id="4b77d-346"><xref:System.Text.Json> хранит упакованный `JsonElement` как для простых, так и для сложных значений при десериализации в <xref:System.Object>, например:</span><span class="sxs-lookup"><span data-stu-id="4b77d-346"><xref:System.Text.Json> stores a boxed `JsonElement` for both primitive and complex values whenever deserializing to <xref:System.Object>, for example:</span></span>

* <span data-ttu-id="4b77d-347">Свойство `object`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-347">An `object` property.</span></span>
* <span data-ttu-id="4b77d-348">Значение словаря `object`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-348">An `object` dictionary value.</span></span>
* <span data-ttu-id="4b77d-349">Тип массива `object`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-349">An `object` array value.</span></span>
* <span data-ttu-id="4b77d-350">Корневой `object`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-350">A root `object`.</span></span>

<span data-ttu-id="4b77d-351">Однако `System.Text.Json` обрабатывает `null` так же, как `Newtonsoft.Json`, и возвращает пустую ссылку, если полезная нагрузка содержит литерал `null` JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-351">However, `System.Text.Json` treats `null` the same as `Newtonsoft.Json` and returns a null reference when the payload has the `null` JSON literal in it.</span></span>

<span data-ttu-id="4b77d-352">Чтобы реализовать определение типа для свойств `object`, создайте преобразователь, как в примере в разделе [Написание пользовательских преобразователей](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="4b77d-352">To implement type inference for `object` properties, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).</span></span>

### <a name="deserialize-null-to-non-nullable-type"></a><span data-ttu-id="4b77d-353">Десериализация значения NULL в тип, не допускающий значения NULL</span><span class="sxs-lookup"><span data-stu-id="4b77d-353">Deserialize null to non-nullable type</span></span>

<span data-ttu-id="4b77d-354">`Newtonsoft.Json` не создает исключение в следующем сценарии:</span><span class="sxs-lookup"><span data-stu-id="4b77d-354">`Newtonsoft.Json` doesn't throw an exception in the following scenario:</span></span>

* <span data-ttu-id="4b77d-355">`NullValueHandling` имеет значение `Ignore`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-355">`NullValueHandling` is set to `Ignore`, and</span></span>
* <span data-ttu-id="4b77d-356">Во время десериализации JSON содержит значение NULL для типа значения, не допускающего значения NULL.</span><span class="sxs-lookup"><span data-stu-id="4b77d-356">During deserialization, the JSON contains a null value for a non-nullable value type.</span></span>

<span data-ttu-id="4b77d-357">В том же сценарии <xref:System.Text.Json> создает исключение.</span><span class="sxs-lookup"><span data-stu-id="4b77d-357">In the same scenario, <xref:System.Text.Json> does throw an exception.</span></span> <span data-ttu-id="4b77d-358">(Соответствующий параметр обработки значений NULL — <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="4b77d-358">(The corresponding null handling setting is <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)</span></span>

<span data-ttu-id="4b77d-359">Если вы владеете типом целевого объекта, лучшим обходным решением будет сделать соответствующее свойство допускающим значение NULL (например, изменить `int` на `int?`).</span><span class="sxs-lookup"><span data-stu-id="4b77d-359">If you own the target type, the best workaround is to make the property in question nullable (for example, change `int` to `int?`).</span></span>

<span data-ttu-id="4b77d-360">Еще один обходной путь — сделать преобразователь для типа, как в следующем примере, который обрабатывает значения NULL для типов `DateTimeOffset`:</span><span class="sxs-lookup"><span data-stu-id="4b77d-360">Another workaround is to make a converter for the type, such as the following example that handles null values for `DateTimeOffset` types:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs)]

<span data-ttu-id="4b77d-361">Зарегистрируйте этот пользовательский преобразователь, [используя атрибут для свойства](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-361">Register this custom converter by [using an attribute on the property](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="4b77d-362">**Примечание.** Предыдущий преобразователь **обрабатывает значения NULL иначе**, чем `Newtonsoft.Json` для POCO, которые указывают значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b77d-362">**Note:** The preceding converter **handles null values differently** than `Newtonsoft.Json` does for POCOs that specify default values.</span></span> <span data-ttu-id="4b77d-363">Например, следующий код представляет целевой объект:</span><span class="sxs-lookup"><span data-stu-id="4b77d-363">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="4b77d-364">Предположим, что следующий JSON десериализуется с помощью предыдущего преобразователя:</span><span class="sxs-lookup"><span data-stu-id="4b77d-364">And suppose the following JSON is deserialized by using the preceding converter:</span></span>

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="4b77d-365">После десериализации свойство `Date` имеет значение 1/1/0001 (`default(DateTimeOffset)`), то есть значение, заданное в конструкторе, перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="4b77d-365">After deserialization, the `Date` property has 1/1/0001 (`default(DateTimeOffset)`), that is, the value set in the constructor is overwritten.</span></span> <span data-ttu-id="4b77d-366">При наличии одних и тех же POCO и JSON десериализация `Newtonsoft.Json` оставляет значение 1/1/2001 в свойстве `Date`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-366">Given the same POCO and JSON, `Newtonsoft.Json` deserialization would leave 1/1/2001 in the `Date` property.</span></span>

### <a name="deserialize-to-immutable-classes-and-structs"></a><span data-ttu-id="4b77d-367">Десериализация в неизменяемые классы и структуры</span><span class="sxs-lookup"><span data-stu-id="4b77d-367">Deserialize to immutable classes and structs</span></span>

<span data-ttu-id="4b77d-368">`Newtonsoft.Json` может выполнять десериализацию в неизменяемые классы и структуры, так как он может использовать конструкторы с параметрами.</span><span class="sxs-lookup"><span data-stu-id="4b77d-368">`Newtonsoft.Json` can deserialize to immutable classes and structs because it can use constructors that have parameters.</span></span> <span data-ttu-id="4b77d-369"><xref:System.Text.Json> поддерживает только открытые конструкторы без параметров.</span><span class="sxs-lookup"><span data-stu-id="4b77d-369"><xref:System.Text.Json> supports only public parameterless constructors.</span></span> <span data-ttu-id="4b77d-370">В качестве обходного решения можно вызвать конструктор с параметрами в пользовательском преобразователе.</span><span class="sxs-lookup"><span data-stu-id="4b77d-370">As a workaround, you can call a constructor with parameters in a custom converter.</span></span>

<span data-ttu-id="4b77d-371">Ниже приведена неизменяемая структура с несколькими параметрами конструктора:</span><span class="sxs-lookup"><span data-stu-id="4b77d-371">Here's an immutable struct with multiple constructor parameters:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePoint.cs#ImmutablePoint)]

<span data-ttu-id="4b77d-372">А вот преобразователь, который сериализует и десериализует эту структуру:</span><span class="sxs-lookup"><span data-stu-id="4b77d-372">And here's a converter that serializes and deserializes this struct:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs)]

<span data-ttu-id="4b77d-373">Зарегистрируйте этот пользовательский преобразователь, [добавив его](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-373">Register this custom converter by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="4b77d-374">Пример подобного преобразователя, обрабатывающего открытые универсальные свойства, см. в разделе [Встроенный преобразователь для пар "ключ-значение"](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).</span><span class="sxs-lookup"><span data-stu-id="4b77d-374">For an example of a similar converter that handles open generic properties, see the [built-in converter for key-value pairs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).</span></span>

### <a name="specify-constructor-to-use"></a><span data-ttu-id="4b77d-375">Указание конструктора для использования</span><span class="sxs-lookup"><span data-stu-id="4b77d-375">Specify constructor to use</span></span>

<span data-ttu-id="4b77d-376">Атрибут `Newtonsoft.Json` `[JsonConstructor]` позволяет указать, какой конструктор вызывать при десериализации в POCO.</span><span class="sxs-lookup"><span data-stu-id="4b77d-376">The `Newtonsoft.Json` `[JsonConstructor]` attribute lets you specify which constructor to call when deserializing to a POCO.</span></span> <span data-ttu-id="4b77d-377"><xref:System.Text.Json> поддерживает только конструкторы без параметров.</span><span class="sxs-lookup"><span data-stu-id="4b77d-377"><xref:System.Text.Json> supports only parameterless constructors.</span></span> <span data-ttu-id="4b77d-378">В качестве обходного решения можно вызвать нужный конструктор в пользовательском преобразователе.</span><span class="sxs-lookup"><span data-stu-id="4b77d-378">As a workaround, you can call whichever constructor you need in a custom converter.</span></span> <span data-ttu-id="4b77d-379">См. пример [десериализации в неизменяемые классы и структуры](#deserialize-to-immutable-classes-and-structs).</span><span class="sxs-lookup"><span data-stu-id="4b77d-379">See the example for [Deserialize to immutable classes and structs](#deserialize-to-immutable-classes-and-structs).</span></span>

### <a name="required-properties"></a><span data-ttu-id="4b77d-380">Обязательные свойства</span><span class="sxs-lookup"><span data-stu-id="4b77d-380">Required properties</span></span>

<span data-ttu-id="4b77d-381">В `Newtonsoft.Json` вы указываете, что свойство является обязательным, задав `Required` для атрибута `[JsonProperty]`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-381">In `Newtonsoft.Json`, you specify that a property is required by setting `Required` on the `[JsonProperty]` attribute.</span></span> <span data-ttu-id="4b77d-382">`Newtonsoft.Json` создает исключение, если в JSON не получено значение для свойства, помеченного как обязательное.</span><span class="sxs-lookup"><span data-stu-id="4b77d-382">`Newtonsoft.Json` throws an exception if no value is received in the JSON for a property marked as required.</span></span>

<span data-ttu-id="4b77d-383"><xref:System.Text.Json> не создает исключение, если для одного из свойств целевого типа не получено значение.</span><span class="sxs-lookup"><span data-stu-id="4b77d-383"><xref:System.Text.Json> doesn't throw an exception if no value is received for one of the properties of the target type.</span></span> <span data-ttu-id="4b77d-384">Например, у вас есть класс `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="4b77d-384">For example, if you have a `WeatherForecast` class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="4b77d-385">Следующий JSON десериализуется без ошибки:</span><span class="sxs-lookup"><span data-stu-id="4b77d-385">The following JSON is deserialized without error:</span></span>

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

<span data-ttu-id="4b77d-386">Чтобы десериализация завершалась ошибкой, когда в JSON отсутствуют свойства `Date`, реализуйте пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="4b77d-386">To make deserialization fail if no `Date` property is in the JSON, implement a custom converter.</span></span> <span data-ttu-id="4b77d-387">Следующий пример кода преобразователя создает исключение, если после десериализации свойство `Date` не задано:</span><span class="sxs-lookup"><span data-stu-id="4b77d-387">The following sample converter code throws an exception if the `Date` property isn't set after deserialization is complete:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs)]

<span data-ttu-id="4b77d-388">Зарегистрируйте этот пользовательский преобразователь, [используя атрибут для класса POCO](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-388">Register this custom converter by [using an attribute on the POCO class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="4b77d-389">Если вы следуете этому шаблону, не передавайте объект options при рекурсивном вызове <xref:System.Text.Json.JsonSerializer.Serialize%2A> или <xref:System.Text.Json.JsonSerializer.Deserialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-389">If you follow this pattern, don't pass in the options object when recursively calling <xref:System.Text.Json.JsonSerializer.Serialize%2A> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A>.</span></span> <span data-ttu-id="4b77d-390">Объект options содержит коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-390">The options object contains the <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> collection.</span></span> <span data-ttu-id="4b77d-391">Если передать его в `Serialize` или `Deserialize`, пользовательский преобразователь вызывает сам себя и делает бесконечный цикл, который приводит к исключению переполнения стека.</span><span class="sxs-lookup"><span data-stu-id="4b77d-391">If you pass it in to `Serialize` or `Deserialize`, the custom converter calls into itself, making an infinite loop that results in a stack overflow exception.</span></span> <span data-ttu-id="4b77d-392">Если параметры по умолчанию нецелесообразны, создайте новый экземпляр параметров с нужными настройками.</span><span class="sxs-lookup"><span data-stu-id="4b77d-392">If the default options are not feasible, create a new instance of the options with the settings that you need.</span></span> <span data-ttu-id="4b77d-393">Этот подход отнимет много времени, так как каждый новый экземпляр кэшируется независимо.</span><span class="sxs-lookup"><span data-stu-id="4b77d-393">This approach will be slow since each new instance caches independently.</span></span>

<span data-ttu-id="4b77d-394">Предыдущий код преобразователя является упрощенным примером.</span><span class="sxs-lookup"><span data-stu-id="4b77d-394">The preceding converter code is a simplified example.</span></span> <span data-ttu-id="4b77d-395">Если необходимо обрабатывать атрибуты (например, [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) или различные параметры (например, пользовательские кодировщики)), потребуется дополнительная логика.</span><span class="sxs-lookup"><span data-stu-id="4b77d-395">Additional logic would be required if you need to handle attributes (such as [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) or different options (such as custom encoders).</span></span> <span data-ttu-id="4b77d-396">Кроме того, пример кода не обрабатывает свойства, для которых в конструкторе задано значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b77d-396">Also, the example code doesn't handle properties for which a default value is set in the constructor.</span></span> <span data-ttu-id="4b77d-397">И этот подход не различает следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="4b77d-397">And this approach doesn't differentiate between the following scenarios:</span></span>

* <span data-ttu-id="4b77d-398">В JSON отсутствует свойство.</span><span class="sxs-lookup"><span data-stu-id="4b77d-398">A property is missing from the JSON.</span></span>
* <span data-ttu-id="4b77d-399">Свойство для типа, не допускающего значения NULL, содержится в JSON, но значение является значением по умолчанию для типа, например ноль для `int`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-399">A property for a non-nullable type is present in the JSON, but the value is the default for the type, such as zero for an `int`.</span></span>
* <span data-ttu-id="4b77d-400">Свойство для типа значения, допускающего значение NULL, содержится в JSON, но значение равно NULL.</span><span class="sxs-lookup"><span data-stu-id="4b77d-400">A property for a nullable value type is present in the JSON, but the value is null.</span></span>

### <a name="conditionally-ignore-a-property"></a><span data-ttu-id="4b77d-401">Условное игнорирование свойства</span><span class="sxs-lookup"><span data-stu-id="4b77d-401">Conditionally ignore a property</span></span>

<span data-ttu-id="4b77d-402">`Newtonsoft.Json` имеет несколько способов условно игнорировать свойство при сериализации или десериализации:</span><span class="sxs-lookup"><span data-stu-id="4b77d-402">`Newtonsoft.Json` has several ways to conditionally ignore a property on serialization or deserialization:</span></span>

* <span data-ttu-id="4b77d-403">`DefaultContractResolver` позволяет выбирать свойства для включения или исключения на основе произвольных критериев.</span><span class="sxs-lookup"><span data-stu-id="4b77d-403">`DefaultContractResolver` lets you select properties to include or exclude, based on arbitrary criteria.</span></span>
* <span data-ttu-id="4b77d-404">Параметры `NullValueHandling` и `DefaultValueHandling` для `JsonSerializerSettings` позволяют указать, что все свойства со значением NULL или значениями по умолчанию должны игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="4b77d-404">The `NullValueHandling` and `DefaultValueHandling` settings on `JsonSerializerSettings` let you specify that all null-value or default-value properties should be ignored.</span></span>
* <span data-ttu-id="4b77d-405">Параметры `NullValueHandling` и `DefaultValueHandling` атрибута `[JsonProperty]` позволяют указать отдельные свойства, которые должны игнорироваться при установке значения NULL или значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b77d-405">The `NullValueHandling` and `DefaultValueHandling` settings on the `[JsonProperty]` attribute let you specify individual properties that should be ignored when set to null or the default value.</span></span>

<span data-ttu-id="4b77d-406"><xref:System.Text.Json> предоставляет следующие способы опустить свойства при сериализации:</span><span class="sxs-lookup"><span data-stu-id="4b77d-406"><xref:System.Text.Json> provides the following ways to omit properties while serializing:</span></span>

* <span data-ttu-id="4b77d-407">Атрибут [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) в свойстве приводит к исключению свойства из JSON во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-407">The [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) attribute on a property causes the property to be omitted from the JSON during serialization.</span></span>
* <span data-ttu-id="4b77d-408">Глобальный параметр [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) позволяет исключить все свойства со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="4b77d-408">The [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) global option lets you exclude all null-value properties.</span></span>
* <span data-ttu-id="4b77d-409">Глобальный параметр [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) позволяет исключить все свойства только для чтения.</span><span class="sxs-lookup"><span data-stu-id="4b77d-409">The [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) global option lets you exclude all read-only properties.</span></span>

<span data-ttu-id="4b77d-410">Эти параметры **не** позволяют:</span><span class="sxs-lookup"><span data-stu-id="4b77d-410">These options **don't** let you:</span></span>

* <span data-ttu-id="4b77d-411">Игнорировать все свойства, имеющие значение по умолчанию для типа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-411">Ignore all properties that have the default value for the type.</span></span>
* <span data-ttu-id="4b77d-412">Игнорировать выбранные свойства, имеющие значение по умолчанию для типа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-412">Ignore selected properties that have the default value for the type.</span></span>
* <span data-ttu-id="4b77d-413">Игнорировать выбранные свойства, если их значение равно NULL.</span><span class="sxs-lookup"><span data-stu-id="4b77d-413">Ignore selected properties if their value is null.</span></span>
* <span data-ttu-id="4b77d-414">Игнорировать выбранные свойства на основе произвольных критериев, вычисляемых во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b77d-414">Ignore selected properties based on arbitrary criteria evaluated at run time.</span></span>

<span data-ttu-id="4b77d-415">Для этой функции можно написать пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="4b77d-415">For that functionality, you can write a custom converter.</span></span> <span data-ttu-id="4b77d-416">Ниже приведен пример POCO и пользовательского преобразователя, демонстрирующий этот подход:</span><span class="sxs-lookup"><span data-stu-id="4b77d-416">Here's a sample POCO and a custom converter for it that illustrates this approach:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

<span data-ttu-id="4b77d-417">Преобразователь вызывает исключение свойства `Summary` из сериализации, если его значение — NULL, пустая строка или "N/A".</span><span class="sxs-lookup"><span data-stu-id="4b77d-417">The converter causes the `Summary` property to be omitted from serialization if its value is null, an empty string, or "N/A".</span></span>

<span data-ttu-id="4b77d-418">Зарегистрируйте этот пользовательский преобразователь, [используя атрибут для класса](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-418">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="4b77d-419">Этот подход требует дополнительной логики, если:</span><span class="sxs-lookup"><span data-stu-id="4b77d-419">This approach requires additional logic if:</span></span>

* <span data-ttu-id="4b77d-420">POCO включает сложные свойства.</span><span class="sxs-lookup"><span data-stu-id="4b77d-420">The POCO includes complex properties.</span></span>
* <span data-ttu-id="4b77d-421">Необходимо выполнять обработку таких атрибутов, как `[JsonIgnore]`, или таких параметров, как пользовательские кодировщики.</span><span class="sxs-lookup"><span data-stu-id="4b77d-421">You need to handle attributes such as `[JsonIgnore]` or options such as custom encoders.</span></span>

### <a name="specify-date-format"></a><span data-ttu-id="4b77d-422">Указание формата даты</span><span class="sxs-lookup"><span data-stu-id="4b77d-422">Specify date format</span></span>

<span data-ttu-id="4b77d-423">`Newtonsoft.Json` предоставляет несколько способов управления сериализацией и десериализации свойств `DateTime` и типов `DateTimeOffset`:</span><span class="sxs-lookup"><span data-stu-id="4b77d-423">`Newtonsoft.Json` provides several ways to control how properties of `DateTime` and `DateTimeOffset` types are serialized and deserialized:</span></span>

* <span data-ttu-id="4b77d-424">Параметр `DateTimeZoneHandling` можно использовать для сериализации всех значений `DateTime` как даты в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="4b77d-424">The `DateTimeZoneHandling` setting can be used to serialize all `DateTime` values as UTC dates.</span></span>
* <span data-ttu-id="4b77d-425">Параметры `DateFormatString` и преобразователи `DateTime` можно использовать для настройки формата строк даты.</span><span class="sxs-lookup"><span data-stu-id="4b77d-425">The `DateFormatString` setting and `DateTime` converters can be used to customize the format of date strings.</span></span>

<span data-ttu-id="4b77d-426">В <xref:System.Text.Json> единственным форматом со встроенной поддержкой является ISO 8601-1:2019, так как он широко используется, выражен однозначно и обеспечивает точные круговые пути.</span><span class="sxs-lookup"><span data-stu-id="4b77d-426">In <xref:System.Text.Json>, the only format that has built-in support is ISO 8601-1:2019 since it's widely adopted, unambiguous, and makes round trips precisely.</span></span> <span data-ttu-id="4b77d-427">Чтобы использовать любой другой формат, создайте пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="4b77d-427">To use any other format, create a custom converter.</span></span> <span data-ttu-id="4b77d-428">Дополнительные сведения см. в разделе [Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md).</span><span class="sxs-lookup"><span data-stu-id="4b77d-428">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>

### <a name="callbacks"></a><span data-ttu-id="4b77d-429">Обратные вызовы</span><span class="sxs-lookup"><span data-stu-id="4b77d-429">Callbacks</span></span>

<span data-ttu-id="4b77d-430">`Newtonsoft.Json` позволяет выполнять пользовательский код в нескольких точках процесса сериализации или десериализации:</span><span class="sxs-lookup"><span data-stu-id="4b77d-430">`Newtonsoft.Json` lets you execute custom code at several points in the serialization or deserialization process:</span></span>

* <span data-ttu-id="4b77d-431">OnDeserializing (в начале десериализации объекта)</span><span class="sxs-lookup"><span data-stu-id="4b77d-431">OnDeserializing (when beginning to deserialize an object)</span></span>
* <span data-ttu-id="4b77d-432">OnDeserialized (после десериализации объекта)</span><span class="sxs-lookup"><span data-stu-id="4b77d-432">OnDeserialized (when finished deserializing an object)</span></span>
* <span data-ttu-id="4b77d-433">OnSerializing (в начале сериализации объекта)</span><span class="sxs-lookup"><span data-stu-id="4b77d-433">OnSerializing (when beginning to serialize an object)</span></span>
* <span data-ttu-id="4b77d-434">OnSerialized (после сериализации объекта)</span><span class="sxs-lookup"><span data-stu-id="4b77d-434">OnSerialized (when finished serializing an object)</span></span>

<span data-ttu-id="4b77d-435">В <xref:System.Text.Json> можно имитировать обратные вызовы, написав пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="4b77d-435">In <xref:System.Text.Json>, you can simulate callbacks by writing a custom converter.</span></span> <span data-ttu-id="4b77d-436">В следующем примере показан пользовательский преобразователь для POCO.</span><span class="sxs-lookup"><span data-stu-id="4b77d-436">The following example shows a custom converter for a POCO.</span></span> <span data-ttu-id="4b77d-437">Этот преобразователь включает код, отображающий сообщение в каждой точке, которая соответствует обратному вызову `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-437">The converter includes code that displays a message at each point that corresponds to a `Newtonsoft.Json` callback.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs)]

<span data-ttu-id="4b77d-438">Зарегистрируйте этот пользовательский преобразователь, [используя атрибут для класса](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-438">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="4b77d-439">Если вы используете пользовательский преобразователь, как в предыдущем примере:</span><span class="sxs-lookup"><span data-stu-id="4b77d-439">If you use a custom converter that follows the preceding sample:</span></span>

* <span data-ttu-id="4b77d-440">Код `OnDeserializing` не имеет доступа к новому экземпляру POCO.</span><span class="sxs-lookup"><span data-stu-id="4b77d-440">The `OnDeserializing` code doesn't have access to the new POCO instance.</span></span> <span data-ttu-id="4b77d-441">Чтобы управлять новым экземпляром POCO в начале десериализации, вставьте этот код в конструктор POCO.</span><span class="sxs-lookup"><span data-stu-id="4b77d-441">To manipulate the new POCO instance at the start of deserialization, put that code in the POCO constructor.</span></span>
* <span data-ttu-id="4b77d-442">Не передавайте объект options при рекурсивном вызове `Serialize` или `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-442">Don't pass in the options object when recursively calling `Serialize` or `Deserialize`.</span></span> <span data-ttu-id="4b77d-443">Объект options содержит коллекцию `Converters`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-443">The options object contains the `Converters` collection.</span></span> <span data-ttu-id="4b77d-444">Если передать его в `Serialize` или `Deserialize`, будет использован преобразователь, создающий бесконечный цикл, который приводит к исключению переполнения стека.</span><span class="sxs-lookup"><span data-stu-id="4b77d-444">If you pass it in to `Serialize` or `Deserialize`, the converter will be used, making an infinite loop that results in a stack overflow exception.</span></span>

### <a name="public-and-non-public-fields"></a><span data-ttu-id="4b77d-445">Открытые и не открытые поля</span><span class="sxs-lookup"><span data-stu-id="4b77d-445">Public and non-public fields</span></span>

<span data-ttu-id="4b77d-446">`Newtonsoft.Json` может выполнять сериализацию и десериализацию полей, а также свойств.</span><span class="sxs-lookup"><span data-stu-id="4b77d-446">`Newtonsoft.Json` can serialize and deserialize fields as well as properties.</span></span> <span data-ttu-id="4b77d-447"><xref:System.Text.Json> работает только с общими свойствами.</span><span class="sxs-lookup"><span data-stu-id="4b77d-447"><xref:System.Text.Json> only works with public properties.</span></span> <span data-ttu-id="4b77d-448">Эта функция может быть предоставлена пользовательскими преобразователями.</span><span class="sxs-lookup"><span data-stu-id="4b77d-448">Custom converters can provide this functionality.</span></span>

### <a name="internal-and-private-property-setters-and-getters"></a><span data-ttu-id="4b77d-449">Методы задания и получения для внутренних и закрытых свойств</span><span class="sxs-lookup"><span data-stu-id="4b77d-449">Internal and private property setters and getters</span></span>

<span data-ttu-id="4b77d-450">`Newtonsoft.Json` может использовать методы задания и получения частных и внутренних свойств с помощью атрибута `JsonProperty`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-450">`Newtonsoft.Json` can use private and internal property setters and getters via the `JsonProperty` attribute.</span></span> <span data-ttu-id="4b77d-451"><xref:System.Text.Json> поддерживает только открытые методы задания.</span><span class="sxs-lookup"><span data-stu-id="4b77d-451"><xref:System.Text.Json> supports only public setters.</span></span> <span data-ttu-id="4b77d-452">Эта функция может быть предоставлена пользовательскими преобразователями.</span><span class="sxs-lookup"><span data-stu-id="4b77d-452">Custom converters can provide this functionality.</span></span>

### <a name="populate-existing-objects"></a><span data-ttu-id="4b77d-453">Заполнение существующих объектов</span><span class="sxs-lookup"><span data-stu-id="4b77d-453">Populate existing objects</span></span>

<span data-ttu-id="4b77d-454">Метод `JsonConvert.PopulateObject` в `Newtonsoft.Json` десериализует документ JSON в существующий экземпляр класса вместо создания нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4b77d-454">The `JsonConvert.PopulateObject` method in `Newtonsoft.Json` deserializes a JSON document to an existing instance of a class, instead of creating a new instance.</span></span> <span data-ttu-id="4b77d-455"><xref:System.Text.Json> всегда создает новый экземпляр целевого типа с помощью открытого конструктора без параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b77d-455"><xref:System.Text.Json> always creates a new instance of the target type by using the default public parameterless constructor.</span></span> <span data-ttu-id="4b77d-456">Пользовательские преобразователи можно десериализовать в существующий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="4b77d-456">Custom converters can deserialize to an existing instance.</span></span>

### <a name="reuse-rather-than-replace-properties"></a><span data-ttu-id="4b77d-457">Повторное использование вместо замены свойств</span><span class="sxs-lookup"><span data-stu-id="4b77d-457">Reuse rather than replace properties</span></span>

<span data-ttu-id="4b77d-458">Параметр `Newtonsoft.Json` `ObjectCreationHandling` позволяет указать, что объекты в свойствах следует использовать повторно, а не заменять во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-458">The `Newtonsoft.Json` `ObjectCreationHandling` setting lets you specify that objects in properties should be reused rather than replaced during deserialization.</span></span> <span data-ttu-id="4b77d-459"><xref:System.Text.Json> всегда заменяет объекты в свойствах.</span><span class="sxs-lookup"><span data-stu-id="4b77d-459"><xref:System.Text.Json> always replaces objects in properties.</span></span>  <span data-ttu-id="4b77d-460">Эта функция может быть предоставлена пользовательскими преобразователями.</span><span class="sxs-lookup"><span data-stu-id="4b77d-460">Custom converters can provide this functionality.</span></span>

### <a name="add-to-collections-without-setters"></a><span data-ttu-id="4b77d-461">Добавление в коллекции без методов задания</span><span class="sxs-lookup"><span data-stu-id="4b77d-461">Add to collections without setters</span></span>

<span data-ttu-id="4b77d-462">Во время десериализации `Newtonsoft.Json` добавляет объекты в коллекцию, даже если свойство не имеет метода задания.</span><span class="sxs-lookup"><span data-stu-id="4b77d-462">During deserialization, `Newtonsoft.Json` adds objects to a collection even if the property has no setter.</span></span> <span data-ttu-id="4b77d-463"><xref:System.Text.Json> игнорирует свойства, у которых нет методов задания.</span><span class="sxs-lookup"><span data-stu-id="4b77d-463"><xref:System.Text.Json> ignores properties that don't have setters.</span></span> <span data-ttu-id="4b77d-464">Эта функция может быть предоставлена пользовательскими преобразователями.</span><span class="sxs-lookup"><span data-stu-id="4b77d-464">Custom converters can provide this functionality.</span></span>

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a><span data-ttu-id="4b77d-465">Сценарии, которые JsonSerializer в настоящее время не поддерживает</span><span class="sxs-lookup"><span data-stu-id="4b77d-465">Scenarios that JsonSerializer currently doesn't support</span></span>

<span data-ttu-id="4b77d-466">В следующих сценариях обходные пути являются нецелесообразными или невозможными.</span><span class="sxs-lookup"><span data-stu-id="4b77d-466">For the following scenarios, workarounds are not practical or possible.</span></span> <span data-ttu-id="4b77d-467">Если вы используете эти функции `Newtonsoft.Json`, миграция будет невозможна без существенных изменений.</span><span class="sxs-lookup"><span data-stu-id="4b77d-467">If you rely on these `Newtonsoft.Json` features, migration will not be possible without significant changes.</span></span>

### <a name="preserve-object-references-and-handle-loops"></a><span data-ttu-id="4b77d-468">Сохранение ссылок на объекты и обработка циклов</span><span class="sxs-lookup"><span data-stu-id="4b77d-468">Preserve object references and handle loops</span></span>

<span data-ttu-id="4b77d-469">По умолчанию `Newtonsoft.Json` сериализуется по значению.</span><span class="sxs-lookup"><span data-stu-id="4b77d-469">By default, `Newtonsoft.Json` serializes by value.</span></span> <span data-ttu-id="4b77d-470">Например, если объект включает два свойства, которые содержат ссылку на один и тот же объект `Person`, значения свойств этого объекта `Person` дублируются в JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-470">For example, if an object contains two properties that contain a reference to the same `Person` object, the values of that `Person` object's properties are duplicated in the JSON.</span></span>

<span data-ttu-id="4b77d-471">У `Newtonsoft.Json` параметр `PreserveReferencesHandling` имеет значение `JsonSerializerSettings`, что позволяет выполнять сериализацию по ссылке:</span><span class="sxs-lookup"><span data-stu-id="4b77d-471">`Newtonsoft.Json` has a `PreserveReferencesHandling` setting on `JsonSerializerSettings` that lets you serialize by reference:</span></span>

* <span data-ttu-id="4b77d-472">Метаданные идентификатора добавляются в JSON, созданный для первого объекта `Person`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-472">An identifier metadata is added to the JSON created for the first `Person` object.</span></span>
* <span data-ttu-id="4b77d-473">JSON, созданный для второго объекта `Person`, содержит ссылку на этот идентификатор вместо значений свойств.</span><span class="sxs-lookup"><span data-stu-id="4b77d-473">The JSON that is created for the second `Person` object contains a reference to that identifier instead of property values.</span></span>

<span data-ttu-id="4b77d-474">`Newtonsoft.Json` также имеет параметр `ReferenceLoopHandling`, который позволяет игнорировать циклические ссылки, а не создавать исключение.</span><span class="sxs-lookup"><span data-stu-id="4b77d-474">`Newtonsoft.Json` also has a `ReferenceLoopHandling` setting that lets you ignore circular references rather than throw an exception.</span></span>

<span data-ttu-id="4b77d-475"><xref:System.Text.Json> поддерживает только сериализацию по значению и создает исключение для циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="4b77d-475"><xref:System.Text.Json> only supports serialization by value and throws an exception for circular references.</span></span>

### <a name="systemruntimeserialization-attributes"></a><span data-ttu-id="4b77d-476">Атрибуты System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="4b77d-476">System.Runtime.Serialization attributes</span></span>

<span data-ttu-id="4b77d-477"><xref:System.Text.Json> не поддерживает атрибуты из пространства имен `System.Runtime.Serialization`, такие как `DataMemberAttribute` и `IgnoreDataMemberAttribute`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-477"><xref:System.Text.Json> doesn't support attributes from the `System.Runtime.Serialization` namespace, such as `DataMemberAttribute` and `IgnoreDataMemberAttribute`.</span></span>

### <a name="octal-numbers"></a><span data-ttu-id="4b77d-478">Числа восьмеричной системы</span><span class="sxs-lookup"><span data-stu-id="4b77d-478">Octal numbers</span></span>

<span data-ttu-id="4b77d-479">`Newtonsoft.Json` обрабатывает числа с начальным нулем как восьмеричные числа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-479">`Newtonsoft.Json` treats numbers with a leading zero as octal numbers.</span></span> <span data-ttu-id="4b77d-480"><xref:System.Text.Json> не допускает начальные нули, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не разрешает их.</span><span class="sxs-lookup"><span data-stu-id="4b77d-480"><xref:System.Text.Json> doesn't allow leading zeroes because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span>

### <a name="missingmemberhandling"></a><span data-ttu-id="4b77d-481">MissingMemberHandling</span><span class="sxs-lookup"><span data-stu-id="4b77d-481">MissingMemberHandling</span></span>

<span data-ttu-id="4b77d-482">`Newtonsoft.Json` можно настроить для создания исключений во время десериализации, если в JSON включены свойства, отсутствующие в целевом типе.</span><span class="sxs-lookup"><span data-stu-id="4b77d-482">`Newtonsoft.Json` can be configured to throw exceptions during deserialization if the JSON includes properties that are missing in the target type.</span></span> <span data-ttu-id="4b77d-483"><xref:System.Text.Json> игнорирует дополнительные свойства в JSON, за исключением случаев, когда используется атрибут [[JsonExtensionData]](system-text-json-how-to.md#handle-overflow-json).</span><span class="sxs-lookup"><span data-stu-id="4b77d-483"><xref:System.Text.Json> ignores extra properties in the JSON, except when you use the [[JsonExtensionData] attribute](system-text-json-how-to.md#handle-overflow-json).</span></span> <span data-ttu-id="4b77d-484">Для функции отсутствующих членов не существует обходного решения.</span><span class="sxs-lookup"><span data-stu-id="4b77d-484">There's no workaround for the missing member feature.</span></span>

### <a name="tracewriter"></a><span data-ttu-id="4b77d-485">TraceWriter</span><span class="sxs-lookup"><span data-stu-id="4b77d-485">TraceWriter</span></span>

<span data-ttu-id="4b77d-486">`Newtonsoft.Json` позволяет выполнять отладку с помощью `TraceWriter` для просмотра журналов, созданных при сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-486">`Newtonsoft.Json` lets you debug by using a `TraceWriter` to view logs that are generated by serialization or deserialization.</span></span> <span data-ttu-id="4b77d-487"><xref:System.Text.Json> не ведет журнал.</span><span class="sxs-lookup"><span data-stu-id="4b77d-487"><xref:System.Text.Json> doesn't do logging.</span></span>

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a><span data-ttu-id="4b77d-488">JsonDocument и JsonElement в сравнении с JToken (например, JObject, JArray)</span><span class="sxs-lookup"><span data-stu-id="4b77d-488">JsonDocument and JsonElement compared to JToken (like JObject, JArray)</span></span>

<span data-ttu-id="4b77d-489"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность выполнять синтаксический анализ и сборку модели DOM **только для чтения** из существующих полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-489"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to parse and build a **read-only** Document Object Model (DOM) from existing JSON payloads.</span></span> <span data-ttu-id="4b77d-490">Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-490">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="4b77d-491">Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-491">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="4b77d-492">Тип `JsonElement` предоставляет интерфейсы API для преобразования текста JSON в общие типы .NET.</span><span class="sxs-lookup"><span data-stu-id="4b77d-492">The `JsonElement` type provides APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="4b77d-493">`JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-493">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

### <a name="jsondocument-is-idisposable"></a><span data-ttu-id="4b77d-494">JsonDocument является IDisposable</span><span class="sxs-lookup"><span data-stu-id="4b77d-494">JsonDocument is IDisposable</span></span>

<span data-ttu-id="4b77d-495">`JsonDocument` создает выполняющееся в памяти представление данных в едином буфере.</span><span class="sxs-lookup"><span data-stu-id="4b77d-495">`JsonDocument` builds an in-memory view of the data into a pooled buffer.</span></span> <span data-ttu-id="4b77d-496">Таким образом, в отличие от `JObject` или `JArray` из `Newtonsoft.Json`, тип `JsonDocument` реализует `IDisposable` и должен использоваться внутри блока using.</span><span class="sxs-lookup"><span data-stu-id="4b77d-496">Therefore, unlike `JObject` or `JArray` from `Newtonsoft.Json`, the `JsonDocument` type implements `IDisposable` and needs to be used inside a using block.</span></span>

<span data-ttu-id="4b77d-497">Возвращайте `JsonDocument` из API только в том случае, если хотите передать владение временем существования и ответственность вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="4b77d-497">Only return a `JsonDocument` from your API if you want to transfer lifetime ownership and dispose responsibility to the caller.</span></span> <span data-ttu-id="4b77d-498">В большинстве случаев это необязательно.</span><span class="sxs-lookup"><span data-stu-id="4b77d-498">In most scenarios, that isn't necessary.</span></span> <span data-ttu-id="4b77d-499">Если вызывающему объекту необходимо работать со всем документом JSON, возвращайте <xref:System.Text.Json.JsonElement.Clone%2A> <xref:System.Text.Json.JsonDocument.RootElement%2A>, то есть <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-499">If the caller needs to work with the entire JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of the <xref:System.Text.Json.JsonDocument.RootElement%2A>, which is a <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="4b77d-500">Если вызывающему объекту необходимо работать с определенным элементом в документе JSON, возвращайте <xref:System.Text.Json.JsonElement.Clone%2A> этого <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-500">If the caller needs to work with a particular element within the JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of that <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="4b77d-501">Если вы возвращаете `RootElement` или вложенный элемент напрямую, не выполняя `Clone`, вызывающий объект не сможет получить доступ к возвращаемому объекту `JsonElement` после того, как `JsonDocument`, которому он принадлежит, будет удален.</span><span class="sxs-lookup"><span data-stu-id="4b77d-501">If you return the `RootElement` or a sub-element directly without making a `Clone`, the caller won't be able to access the returned `JsonElement` after the `JsonDocument` that owns it is disposed.</span></span>

<span data-ttu-id="4b77d-502">Ниже приведен пример, в котором необходимо сделать `Clone`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-502">Here's an example that requires you to make a `Clone`:</span></span>

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

<span data-ttu-id="4b77d-503">Приведенный выше код ждет `JsonElement`, содержащий свойство `fileName`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-503">The preceding code expects a `JsonElement` that contains a `fileName` property.</span></span> <span data-ttu-id="4b77d-504">Он открывает JSON-файл и создает `JsonDocument`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-504">It opens the JSON file and creates a `JsonDocument`.</span></span> <span data-ttu-id="4b77d-505">Метод предполагает, что вызывающий объект хочет работать со всем документом, поэтому он возвращает `Clone` `RootElement`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-505">The method assumes that the caller wants to work with the entire document, so it returns the `Clone` of the `RootElement`.</span></span>

<span data-ttu-id="4b77d-506">Если вы получаете `JsonElement` и возвращаете вложенный элемент, нет необходимости возвращать `Clone` вложенного элемента.</span><span class="sxs-lookup"><span data-stu-id="4b77d-506">If you receive a `JsonElement` and are returning a sub-element, it's not necessary to return a `Clone` of the sub-element.</span></span> <span data-ttu-id="4b77d-507">Вызывающий объект отвечает за поддержание активности `JsonDocument`, которому принадлежит переданный `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-507">The caller is responsible for keeping alive the `JsonDocument` that the passed-in `JsonElement` belongs to.</span></span> <span data-ttu-id="4b77d-508">Пример:</span><span class="sxs-lookup"><span data-stu-id="4b77d-508">For example:</span></span>

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a><span data-ttu-id="4b77d-509">JsonDocument доступен только для чтения</span><span class="sxs-lookup"><span data-stu-id="4b77d-509">JsonDocument is read-only</span></span>

<span data-ttu-id="4b77d-510">Модель DOM <xref:System.Text.Json> не может добавлять, удалять или изменять элементы JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-510">The <xref:System.Text.Json> DOM can't add, remove, or modify JSON elements.</span></span> <span data-ttu-id="4b77d-511">Она разработана таким образом для повышения производительности и сокращения количества распределений для анализа полезных данных JSON обычного размера (то есть < 1 МБ).</span><span class="sxs-lookup"><span data-stu-id="4b77d-511">It's designed this way for performance and to reduce allocations for parsing common JSON payload sizes (that is, < 1 MB).</span></span> <span data-ttu-id="4b77d-512">Если в вашем сценарии используется изменяемая модель DOM, возможны следующие обходные пути.</span><span class="sxs-lookup"><span data-stu-id="4b77d-512">If your scenario currently uses a modifiable DOM, one of the following workarounds might be feasible:</span></span>

* <span data-ttu-id="4b77d-513">Чтобы создать `JsonDocument` с нуля (то есть без передачи существующих полезных данных JSON в метод `Parse`), напишите текст JSON с помощью `Utf8JsonWriter` и проанализируйте выходные данные, чтобы создать новый `JsonDocument`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-513">To build a `JsonDocument` from scratch (that is, without passing in an existing JSON payload to the `Parse` method), write the JSON text by using the `Utf8JsonWriter` and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="4b77d-514">Чтобы изменить существующий `JsonDocument`, используйте его для написания текста JSON, внося изменения во время написания, и проанализируйте выходные данные для создания нового `JsonDocument`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-514">To modify an existing `JsonDocument`, use it to write JSON text, making changes while you write, and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="4b77d-515">Сведения о слиянии существующих документов JSON, эквивалентных API `JObject.Merge` или `JContainer.Merge` из `Newtonsoft.Json`, см. в [этой проблеме GitHub](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).</span><span class="sxs-lookup"><span data-stu-id="4b77d-515">To merge existing JSON documents, equivalent to the `JObject.Merge` or `JContainer.Merge` APIs from `Newtonsoft.Json`, see [this GitHub issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).</span></span>

### <a name="jsonelement-is-a-union-struct"></a><span data-ttu-id="4b77d-516">JsonElement является структурой объединения</span><span class="sxs-lookup"><span data-stu-id="4b77d-516">JsonElement is a union struct</span></span>

<span data-ttu-id="4b77d-517">`JsonDocument` предоставляет `RootElement` как свойство типа <xref:System.Text.Json.JsonElement>, которое представляет собой объединение, тип структуры, охватывающий любой элемент JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-517">`JsonDocument` exposes the `RootElement` as a property of type <xref:System.Text.Json.JsonElement>, which is a union, struct type that encompasses any JSON element.</span></span> <span data-ttu-id="4b77d-518">`Newtonsoft.Json` использует выделенные иерархические типы, такие как `JObject`, `JArray`, `JToken` и т. д.</span><span class="sxs-lookup"><span data-stu-id="4b77d-518">`Newtonsoft.Json` uses dedicated hierarchical types like `JObject`,`JArray`, `JToken`, and so forth.</span></span> <span data-ttu-id="4b77d-519">`JsonElement` можно использовать для поиска и перечисления, а с помощью `JsonElement` можно материализовывать элементы JSON в типы .NET.</span><span class="sxs-lookup"><span data-stu-id="4b77d-519">`JsonElement` is what you can search and enumerate over, and you can use `JsonElement` to materialize JSON elements into .NET types.</span></span>

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a><span data-ttu-id="4b77d-520">Поиск вложенных элементов в JsonDocument и JsonElement</span><span class="sxs-lookup"><span data-stu-id="4b77d-520">How to search a JsonDocument and JsonElement for sub-elements</span></span>

<span data-ttu-id="4b77d-521">Поиск токенов JSON с помощью `JObject` или `JArray` из `Newtonsoft.Json`, как правило, выполняется относительно быстро, так как они присутствуют в словаре.</span><span class="sxs-lookup"><span data-stu-id="4b77d-521">Searches for JSON tokens using `JObject` or `JArray` from `Newtonsoft.Json` tend to be relatively fast because they're lookups in some dictionary.</span></span> <span data-ttu-id="4b77d-522">Зато поиск по `JsonElement` требует последовательного поиска свойств и, следовательно, занимает относительно много времени (например, при использовании `TryGetProperty`).</span><span class="sxs-lookup"><span data-stu-id="4b77d-522">By comparison, searches on `JsonElement` require a sequential search of the properties and hence is relatively slow (for example when using `TryGetProperty`).</span></span> <span data-ttu-id="4b77d-523"><xref:System.Text.Json> предназначен для сокращения времени начального анализа, а не времени поиска.</span><span class="sxs-lookup"><span data-stu-id="4b77d-523"><xref:System.Text.Json> is designed to minimize initial parse time rather than lookup time.</span></span> <span data-ttu-id="4b77d-524">Поэтому рекомендуется использовать следующие подходы для оптимизации производительности при поиске по объекту `JsonDocument`:</span><span class="sxs-lookup"><span data-stu-id="4b77d-524">Therefore, use the following approaches to optimize performance when searching through a `JsonDocument` object:</span></span>

* <span data-ttu-id="4b77d-525">Используйте встроенные перечислители (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> и <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) вместо создания собственных индексов или циклов.</span><span class="sxs-lookup"><span data-stu-id="4b77d-525">Use the built-in enumerators (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> and <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) rather than doing your own indexing or loops.</span></span>
* <span data-ttu-id="4b77d-526">Не выполняйте последовательный поиск по всему `JsonDocument` в каждом свойстве с помощью `RootElement`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-526">Don't do a sequential search on the whole `JsonDocument` through every property by using `RootElement`.</span></span> <span data-ttu-id="4b77d-527">Вместо этого выполните поиск по вложенным объектам JSON на основе известной структуры данных JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-527">Instead, search on nested JSON objects based on the known structure of the JSON data.</span></span> <span data-ttu-id="4b77d-528">Например, если вы ищете свойство `Grade` в объектах `Student`, пройдите по объектам `Student` и получите значение `Grade` для каждого из них, вместо того, чтобы проходить по всем объектам `JsonElement` в поисках свойств `Grade`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-528">For example, if you're looking for a `Grade` property in `Student` objects, loop through the `Student` objects and get the value of `Grade` for each, rather than searching through all `JsonElement` objects looking for `Grade` properties.</span></span> <span data-ttu-id="4b77d-529">Последний метод приведет к ненужным проходам по тем же данным.</span><span class="sxs-lookup"><span data-stu-id="4b77d-529">Doing the latter will result in unnecessary passes over the same data.</span></span>

<span data-ttu-id="4b77d-530">Пример кода см. в разделе [Использование JsonDocument для доступа к данным](system-text-json-how-to.md#use-jsondocument-for-access-to-data).</span><span class="sxs-lookup"><span data-stu-id="4b77d-530">For a code example, see [Use JsonDocument for access to data](system-text-json-how-to.md#use-jsondocument-for-access-to-data).</span></span>

## <a name="utf8jsonreader-compared-to-jsontextreader"></a><span data-ttu-id="4b77d-531">Сравнение Utf8JsonReader и JsonTextReader</span><span class="sxs-lookup"><span data-stu-id="4b77d-531">Utf8JsonReader compared to JsonTextReader</span></span>

<span data-ttu-id="4b77d-532"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это последовательный модуль чтения текста JSON в кодировке UTF-8 с высокой производительностью и низким уровнем распределения, при этом чтение выполняется из [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) или [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601).</span><span class="sxs-lookup"><span data-stu-id="4b77d-532"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601).</span></span> <span data-ttu-id="4b77d-533">`Utf8JsonReader` — это низкоуровневый тип, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы.</span><span class="sxs-lookup"><span data-stu-id="4b77d-533">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span>

<span data-ttu-id="4b77d-534">В следующих разделах описываются рекомендуемые шаблоны программирования для использования `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-534">The following sections explain recommended programming patterns for using `Utf8JsonReader`.</span></span>

### <a name="utf8jsonreader-is-a-ref-struct"></a><span data-ttu-id="4b77d-535">Utf8JsonReader является структурой ссылок</span><span class="sxs-lookup"><span data-stu-id="4b77d-535">Utf8JsonReader is a ref struct</span></span>

<span data-ttu-id="4b77d-536">Поскольку тип `Utf8JsonReader` является *структурой ссылок*, он имеет [определенные ограничения](../../csharp/language-reference/builtin-types/struct.md#ref-struct).</span><span class="sxs-lookup"><span data-stu-id="4b77d-536">Because the `Utf8JsonReader` type is a *ref struct*, it has [certain limitations](../../csharp/language-reference/builtin-types/struct.md#ref-struct).</span></span> <span data-ttu-id="4b77d-537">Например, он не может храниться как поле в классе или структуре, отличной от структуры ссылки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-537">For example, it can't be stored as a field on a class or struct other than a ref struct.</span></span> <span data-ttu-id="4b77d-538">Для достижения высокой производительности этот тип должен быть `ref struct`, поскольку ему необходимо кэшировать входной объект [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), который сам по себе является структурой ссылок.</span><span class="sxs-lookup"><span data-stu-id="4b77d-538">To achieve high performance, this type must be a `ref struct` since it needs to cache the input [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), which itself is a ref struct.</span></span> <span data-ttu-id="4b77d-539">Кроме того, этот тип является изменяемым, так как имеет состояние.</span><span class="sxs-lookup"><span data-stu-id="4b77d-539">In addition, this type is mutable since it holds state.</span></span> <span data-ttu-id="4b77d-540">Поэтому **передавайте его по ссылке**, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="4b77d-540">Therefore, **pass it by ref** rather than by value.</span></span> <span data-ttu-id="4b77d-541">Передача его по значению приведет к копированию структуры, и изменения состояния не будут видны вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="4b77d-541">Passing it by value would result in a struct copy and the state changes would not be visible to the caller.</span></span> <span data-ttu-id="4b77d-542">Это отличается от `Newtonsoft.Json`, так как `Newtonsoft.Json` `JsonTextReader` является классом.</span><span class="sxs-lookup"><span data-stu-id="4b77d-542">This differs from `Newtonsoft.Json` since the `Newtonsoft.Json` `JsonTextReader` is a class.</span></span> <span data-ttu-id="4b77d-543">Дополнительные сведения об использовании структур ссылок см. в статье [Написание безопасного и эффективного кода C#](../../csharp/write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="4b77d-543">For more information about how to use ref structs, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>

### <a name="read-utf-8-text"></a><span data-ttu-id="4b77d-544">Чтение текста UTF-8</span><span class="sxs-lookup"><span data-stu-id="4b77d-544">Read UTF-8 text</span></span>

<span data-ttu-id="4b77d-545">Для достижения наилучшей производительности при использовании `Utf8JsonReader` читайте полезные данные JSON, уже закодированные как текст UTF-8, а не как строки UTF-16.</span><span class="sxs-lookup"><span data-stu-id="4b77d-545">To achieve the best possible performance while using the `Utf8JsonReader`, read JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="4b77d-546">Пример кода см. в разделе [Фильтрация данных с помощью Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).</span><span class="sxs-lookup"><span data-stu-id="4b77d-546">For a code example, see [Filter data using Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).</span></span>

### <a name="read-with-a-stream-or-pipereader"></a><span data-ttu-id="4b77d-547">Чтение с помощью Stream или PipeReader</span><span class="sxs-lookup"><span data-stu-id="4b77d-547">Read with a Stream or PipeReader</span></span>

<span data-ttu-id="4b77d-548">`Utf8JsonReader` поддерживает чтение [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) или [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) в кодировке UTF-8 (результат чтения из <xref:System.IO.Pipelines.PipeReader>).</span><span class="sxs-lookup"><span data-stu-id="4b77d-548">The `Utf8JsonReader` supports reading from a UTF-8 encoded [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>).</span></span>

<span data-ttu-id="4b77d-549">Для синхронного чтения можно считывать полезные данные JSON до конца потока в массив байтов и передать его в модуль чтения.</span><span class="sxs-lookup"><span data-stu-id="4b77d-549">For synchronous reading, you could read the JSON payload until the end of the stream into a byte array and pass that into the reader.</span></span> <span data-ttu-id="4b77d-550">Для чтения из строки (в кодировке UTF-16) вызовите <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A>,</span><span class="sxs-lookup"><span data-stu-id="4b77d-550">For reading from a string (which is encoded as UTF-16), call <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A></span></span> <span data-ttu-id="4b77d-551">чтобы сначала перекодировать строку в массив байтов в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4b77d-551">to first transcode the string to a UTF-8 encoded byte array.</span></span> <span data-ttu-id="4b77d-552">Затем передайте данные в `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-552">Then pass that to the `Utf8JsonReader`.</span></span>

<span data-ttu-id="4b77d-553">Поскольку `Utf8JsonReader` считает входные данные текстом JSON, метка порядка байтов UTF-8 считается недопустимым JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-553">Since the `Utf8JsonReader` considers the input to be JSON text, a UTF-8 byte order mark (BOM) is considered invalid JSON.</span></span> <span data-ttu-id="4b77d-554">Вызывающий объект должен использовать фильтр, прежде чем передавать данные в модуль чтения.</span><span class="sxs-lookup"><span data-stu-id="4b77d-554">The caller needs to filter that out before passing the data to the reader.</span></span>

<span data-ttu-id="4b77d-555">Примеры кода см. в разделе [Использование Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).</span><span class="sxs-lookup"><span data-stu-id="4b77d-555">For code examples, see [Use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).</span></span>

### <a name="read-with-multi-segment-readonlysequence"></a><span data-ttu-id="4b77d-556">Чтение с помощью ReadOnlySequence с несколькими сегментами</span><span class="sxs-lookup"><span data-stu-id="4b77d-556">Read with multi-segment ReadOnlySequence</span></span>

<span data-ttu-id="4b77d-557">Если входные данные JSON являются [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), к каждому элементу JSON можно получить доступ из свойства `ValueSpan` в модуле чтения при проходе цикла чтения.</span><span class="sxs-lookup"><span data-stu-id="4b77d-557">If your JSON input is a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), each JSON element can be accessed from the `ValueSpan` property on the reader as you go through the read loop.</span></span> <span data-ttu-id="4b77d-558">Однако если входными данными является [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (результат чтения из <xref:System.IO.Pipelines.PipeReader>), некоторые элементы JSON могут создать несколько сегментов объекта `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-558">However, if your input is a [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>), some JSON elements might straddle multiple segments of the `ReadOnlySequence<byte>` object.</span></span> <span data-ttu-id="4b77d-559">Эти элементы не будут доступны из <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> в непрерывном блоке памяти.</span><span class="sxs-lookup"><span data-stu-id="4b77d-559">These elements would not be accessible from <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in a contiguous memory block.</span></span> <span data-ttu-id="4b77d-560">Вместо этого каждый раз, когда у вас есть `ReadOnlySequence<byte>` с несколькими сегментами в качестве входных данных, следует опросить свойство <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> в модуле чтения, чтобы выяснить, как получить доступ к текущему элементу JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-560">Instead, whenever you have a multi-segment `ReadOnlySequence<byte>` as input, poll the <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> property on the reader to figure out how to access the current JSON element.</span></span> <span data-ttu-id="4b77d-561">Вот рекомендуемый шаблон:</span><span class="sxs-lookup"><span data-stu-id="4b77d-561">Here's a recommended pattern:</span></span>

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a><span data-ttu-id="4b77d-562">Использование ValueTextEquals для поиска имени свойства</span><span class="sxs-lookup"><span data-stu-id="4b77d-562">Use ValueTextEquals for property name lookups</span></span>

<span data-ttu-id="4b77d-563">Не используйте <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> для побайтового сравнения путем вызова <xref:System.MemoryExtensions.SequenceEqual%2A> для поиска имени свойства.</span><span class="sxs-lookup"><span data-stu-id="4b77d-563">Don't use <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> to do byte-by-byte comparisons by calling <xref:System.MemoryExtensions.SequenceEqual%2A> for property name lookups.</span></span> <span data-ttu-id="4b77d-564">Вместо этого вызовите <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>, так как этот метод отменяет экранирование всех символов, которые экранированы в JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-564">Call <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> instead, because that method unescapes any characters that are escaped in the JSON.</span></span> <span data-ttu-id="4b77d-565">Ниже приведен пример, демонстрирующий поиск свойства с именем name:</span><span class="sxs-lookup"><span data-stu-id="4b77d-565">Here's an example that shows how to search for a property that is named "name":</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a><span data-ttu-id="4b77d-566">Считывание значений NULL в типы значений, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="4b77d-566">Read null values into nullable value types</span></span>

<span data-ttu-id="4b77d-567">`Newtonsoft.Json` предоставляет API, которые возвращают <xref:System.Nullable%601>, например `ReadAsBoolean`, который обрабатывает `Null` `TokenType`, возвращая `bool?`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-567">`Newtonsoft.Json` provides APIs that return <xref:System.Nullable%601>, such as `ReadAsBoolean`, which handles a `Null` `TokenType` for you by returning a `bool?`.</span></span> <span data-ttu-id="4b77d-568">Встроенные API `System.Text.Json` возвращают только типы значений, не допускающие значения NULL.</span><span class="sxs-lookup"><span data-stu-id="4b77d-568">The built-in `System.Text.Json` APIs return only non-nullable value types.</span></span> <span data-ttu-id="4b77d-569">Например, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> возвращает `bool`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-569">For example, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> returns a `bool`.</span></span> <span data-ttu-id="4b77d-570">Он вызывает исключение, если обнаруживает `Null` в JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-570">It throws an exception if it finds `Null` in the JSON.</span></span> <span data-ttu-id="4b77d-571">В следующих примерах показаны два способа обработки значений NULL: возврат типа значения, допускающего значение NULL, и возврат значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="4b77d-571">The following examples show two ways to handle nulls, one by returning a nullable value type and one by returning the default value:</span></span>

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a><span data-ttu-id="4b77d-572">Настройка для различных версий</span><span class="sxs-lookup"><span data-stu-id="4b77d-572">Multi-targeting</span></span>

<span data-ttu-id="4b77d-573">Если необходимо продолжить использование `Newtonsoft.Json` для определенных целевых платформ, можно выбрать несколько версий и создать две реализации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-573">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="4b77d-574">Однако это нестандартный подход, и потребуется несколько `#ifdefs` и дублирование источника.</span><span class="sxs-lookup"><span data-stu-id="4b77d-574">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="4b77d-575">Одним из способов совместного использования максимально возможного объема кода является создание оболочки `ref struct` вокруг `Utf8JsonReader` и `Newtonsoft.Json` `JsonTextReader`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-575">One way to share as much code as possible is to create a `ref struct` wrapper around `Utf8JsonReader` and `Newtonsoft.Json` `JsonTextReader`.</span></span> <span data-ttu-id="4b77d-576">Эта оболочка будет объединять общедоступную контактную зону при изоляции различий в поведении.</span><span class="sxs-lookup"><span data-stu-id="4b77d-576">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="4b77d-577">Это позволяет изолировать изменения, сведя их, в основном, к созданию типа, а также передаче нового типа по ссылке.</span><span class="sxs-lookup"><span data-stu-id="4b77d-577">This lets you isolate the changes mainly to the construction of the type, along with passing the new type around by reference.</span></span> <span data-ttu-id="4b77d-578">Это шаблон, которому следует библиотека [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/):</span><span class="sxs-lookup"><span data-stu-id="4b77d-578">This is the pattern that the [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="4b77d-579">UnifiedJsonReader.JsonTextReader.cs</span><span class="sxs-lookup"><span data-stu-id="4b77d-579">UnifiedJsonReader.JsonTextReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [<span data-ttu-id="4b77d-580">UnifiedJsonReader.Utf8JsonReader.cs</span><span class="sxs-lookup"><span data-stu-id="4b77d-580">UnifiedJsonReader.Utf8JsonReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a><span data-ttu-id="4b77d-581">Сравнение Utf8JsonWriter и JsonTextWriter</span><span class="sxs-lookup"><span data-stu-id="4b77d-581">Utf8JsonWriter compared to JsonTextWriter</span></span>

<span data-ttu-id="4b77d-582"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записать текст JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-582"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="4b77d-583">Модуль записи — это низкоуровневый тип, с помощью которого можно создавать пользовательские сериализаторы.</span><span class="sxs-lookup"><span data-stu-id="4b77d-583">The writer is a low-level type that can be used to build custom serializers.</span></span>

<span data-ttu-id="4b77d-584">В следующих разделах описываются рекомендуемые шаблоны программирования для использования `Utf8JsonWriter`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-584">The following sections explain recommended programming patterns for using `Utf8JsonWriter`.</span></span>

### <a name="write-with-utf-8-text"></a><span data-ttu-id="4b77d-585">Запись с помощью текста UTF-8</span><span class="sxs-lookup"><span data-stu-id="4b77d-585">Write with UTF-8 text</span></span>

<span data-ttu-id="4b77d-586">Для достижения наилучшей производительности при использовании `Utf8JsonWriter` записывайте полезные данные JSON, уже закодированные как текст UTF-8, а не как строки UTF-16.</span><span class="sxs-lookup"><span data-stu-id="4b77d-586">To achieve the best possible performance while using the `Utf8JsonWriter`, write JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="4b77d-587">Используйте <xref:System.Text.Json.JsonEncodedText>, чтобы кэшировать и предварительно закодировать известные имена и значения свойств строки как статические, а затем передать их в модуль записи вместо использования строковых литералов UTF-16.</span><span class="sxs-lookup"><span data-stu-id="4b77d-587">Use <xref:System.Text.Json.JsonEncodedText> to cache and pre-encode known string property names and values as statics, and pass those to the writer, rather than using UTF-16 string literals.</span></span> <span data-ttu-id="4b77d-588">Это быстрее, чем кэширование и использование байтовых массивов UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4b77d-588">This is faster than caching and using UTF-8 byte arrays.</span></span>

<span data-ttu-id="4b77d-589">Этот подход также работает, если необходимо выполнить пользовательское экранирование.</span><span class="sxs-lookup"><span data-stu-id="4b77d-589">This approach also works if you need to do custom escaping.</span></span> <span data-ttu-id="4b77d-590">`System.Text.Json` не позволяет отключить экранирование при записи строки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-590">`System.Text.Json` doesn't let you disable escaping while writing a string.</span></span> <span data-ttu-id="4b77d-591">Однако можно передать собственный пользовательский <xref:System.Text.Encodings.Web.JavaScriptEncoder> в качестве параметра для модуля записи или создать собственный `JsonEncodedText`, который использует `JavascriptEncoder` для выполнения экранирования, а затем написать `JsonEncodedText` вместо строки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-591">However, you could pass in your own custom <xref:System.Text.Encodings.Web.JavaScriptEncoder> as an option to the writer, or create your own `JsonEncodedText` that uses your `JavascriptEncoder` to do the escaping, and then write the `JsonEncodedText` instead of the string.</span></span> <span data-ttu-id="4b77d-592">Дополнительные сведения см. в статье [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).</span><span class="sxs-lookup"><span data-stu-id="4b77d-592">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="write-raw-values"></a><span data-ttu-id="4b77d-593">Запись необработанных значений</span><span class="sxs-lookup"><span data-stu-id="4b77d-593">Write raw values</span></span>

<span data-ttu-id="4b77d-594">Метод `Newtonsoft.Json` `WriteRawValue` записывает необработанный код JSON, где ожидается значение.</span><span class="sxs-lookup"><span data-stu-id="4b77d-594">The `Newtonsoft.Json` `WriteRawValue` method writes raw JSON where a value is expected.</span></span> <span data-ttu-id="4b77d-595"><xref:System.Text.Json> не имеет прямого эквивалента, но ниже приведено обходное решение, обеспечивающее запись только допустимого JSON:</span><span class="sxs-lookup"><span data-stu-id="4b77d-595"><xref:System.Text.Json> has no direct equivalent, but here's a workaround that ensures only valid JSON is written:</span></span>

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a><span data-ttu-id="4b77d-596">Настройка экранирования символов</span><span class="sxs-lookup"><span data-stu-id="4b77d-596">Customize character escaping</span></span>

<span data-ttu-id="4b77d-597">Параметр [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) `JsonTextWriter` предлагает варианты для экранирования всех символов, не являющихся символами ASCII, **или** символов HTML.</span><span class="sxs-lookup"><span data-stu-id="4b77d-597">The [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) setting of `JsonTextWriter` offers options to escape all non-ASCII characters **or** HTML characters.</span></span> <span data-ttu-id="4b77d-598">По умолчанию `Utf8JsonWriter` экранирует все символы, отличные от ASCII, **и** символы HTML.</span><span class="sxs-lookup"><span data-stu-id="4b77d-598">By default, `Utf8JsonWriter` escapes all non-ASCII **and** HTML characters.</span></span> <span data-ttu-id="4b77d-599">Такое экранирование выполняется в целях глубокой защиты.</span><span class="sxs-lookup"><span data-stu-id="4b77d-599">This escaping is done for defense-in-depth security reasons.</span></span> <span data-ttu-id="4b77d-600">Чтобы указать другую политику экранирования, создайте <xref:System.Text.Encodings.Web.JavaScriptEncoder> и задайте <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-600">To specify a different escaping policy, create a <xref:System.Text.Encodings.Web.JavaScriptEncoder> and set <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4b77d-601">Дополнительные сведения см. в статье [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).</span><span class="sxs-lookup"><span data-stu-id="4b77d-601">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="customize-json-format"></a><span data-ttu-id="4b77d-602">Настройка формата JSON</span><span class="sxs-lookup"><span data-stu-id="4b77d-602">Customize JSON format</span></span>

<span data-ttu-id="4b77d-603">`JsonTextWriter` включает следующие параметры, для которых `Utf8JsonWriter` не имеет эквивалента:</span><span class="sxs-lookup"><span data-stu-id="4b77d-603">`JsonTextWriter` includes the following settings, for which `Utf8JsonWriter` has no equivalent:</span></span>

* <span data-ttu-id="4b77d-604">[Отступ](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) — задает количество символов для отступа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-604">[Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - Specifies how many characters to indent.</span></span> <span data-ttu-id="4b77d-605">`Utf8JsonWriter` всегда имеет 2-символьный отступ.</span><span class="sxs-lookup"><span data-stu-id="4b77d-605">`Utf8JsonWriter` always does 2-character indentation.</span></span>
* <span data-ttu-id="4b77d-606">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) — указывает символ, используемый для отступа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-606">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - Specifies the character to use for indentation.</span></span>  <span data-ttu-id="4b77d-607">`Utf8JsonWriter` всегда использует пробелы.</span><span class="sxs-lookup"><span data-stu-id="4b77d-607">`Utf8JsonWriter` always uses whitespace.</span></span>
* <span data-ttu-id="4b77d-608">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) — указывает символ, используемый для заключения строковых значений.</span><span class="sxs-lookup"><span data-stu-id="4b77d-608">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - Specifies the character to use to surround string values.</span></span>  <span data-ttu-id="4b77d-609">`Utf8JsonWriter` всегда использует двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-609">`Utf8JsonWriter` always uses double quotes.</span></span>
* <span data-ttu-id="4b77d-610">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) — указывает, следует ли заключать имена свойств в кавычки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-610">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - Specifies whether or not to surround property names with quotes.</span></span>  <span data-ttu-id="4b77d-611">`Utf8JsonWriter` всегда заключает их в кавычки.</span><span class="sxs-lookup"><span data-stu-id="4b77d-611">`Utf8JsonWriter` always surrounds them with quotes.</span></span>

<span data-ttu-id="4b77d-612">Не существует обходных решений, которые позволяют настроить JSON, созданный `Utf8JsonWriter` такими методами.</span><span class="sxs-lookup"><span data-stu-id="4b77d-612">There are no workarounds that would let you customize the JSON produced by `Utf8JsonWriter` in these ways.</span></span>

### <a name="write-null-values"></a><span data-ttu-id="4b77d-613">Запись значений NULL</span><span class="sxs-lookup"><span data-stu-id="4b77d-613">Write null values</span></span>

<span data-ttu-id="4b77d-614">Чтобы записать значения NULL с помощью `Utf8JsonWriter`, вызовите:</span><span class="sxs-lookup"><span data-stu-id="4b77d-614">To write null values by using `Utf8JsonWriter`, call:</span></span>

* <span data-ttu-id="4b77d-615"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> для записи пары "ключ-значение" со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="4b77d-615"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> to write a key-value pair with null as the value.</span></span>
* <span data-ttu-id="4b77d-616"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> для записи значения NULL в качестве элемента массива JSON.</span><span class="sxs-lookup"><span data-stu-id="4b77d-616"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> to write null as an element of a JSON array.</span></span>

<span data-ttu-id="4b77d-617">Для строкового свойства, если строка имеет значение NULL, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> и <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> эквивалентны `WriteNull` и `WriteNullValue`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-617">For a string property, if the string is null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> and <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> are equivalent to `WriteNull` and `WriteNullValue`.</span></span>

### <a name="write-timespan-uri-or-char-values"></a><span data-ttu-id="4b77d-618">Запись значений TimeSpan, URI или char</span><span class="sxs-lookup"><span data-stu-id="4b77d-618">Write Timespan, Uri, or char values</span></span>

<span data-ttu-id="4b77d-619">`JsonTextWriter` предоставляет методы `WriteValue` для значений [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm) и [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm).</span><span class="sxs-lookup"><span data-stu-id="4b77d-619">`JsonTextWriter` provides `WriteValue` methods for [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm), and [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) values.</span></span> <span data-ttu-id="4b77d-620">`Utf8JsonWriter` не имеет эквивалентных методов.</span><span class="sxs-lookup"><span data-stu-id="4b77d-620">`Utf8JsonWriter` doesn't have equivalent methods.</span></span> <span data-ttu-id="4b77d-621">Вместо этого следует отформатировать эти значения как строки (например, вызвав `ToString()`) и вызвать <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b77d-621">Instead, format these values as strings (by calling `ToString()`, for example) and call <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.</span></span>

### <a name="multi-targeting"></a><span data-ttu-id="4b77d-622">Настройка для различных версий</span><span class="sxs-lookup"><span data-stu-id="4b77d-622">Multi-targeting</span></span>

<span data-ttu-id="4b77d-623">Если необходимо продолжить использование `Newtonsoft.Json` для определенных целевых платформ, можно выбрать несколько версий и создать две реализации.</span><span class="sxs-lookup"><span data-stu-id="4b77d-623">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="4b77d-624">Однако это нестандартный подход, и потребуется несколько `#ifdefs` и дублирование источника.</span><span class="sxs-lookup"><span data-stu-id="4b77d-624">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="4b77d-625">Одним из способов совместного использования максимально возможного объема кода является создание оболочки вокруг `Utf8JsonWriter` и `Newtonsoft` `JsonTextWriter`.</span><span class="sxs-lookup"><span data-stu-id="4b77d-625">One way to share as much code as possible is to create a wrapper around `Utf8JsonWriter` and `Newtonsoft` `JsonTextWriter`.</span></span> <span data-ttu-id="4b77d-626">Эта оболочка будет объединять общедоступную контактную зону при изоляции различий в поведении.</span><span class="sxs-lookup"><span data-stu-id="4b77d-626">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="4b77d-627">Это позволяет изолировать изменения и свести их, в основном, к созданию типа.</span><span class="sxs-lookup"><span data-stu-id="4b77d-627">This lets you isolate the changes mainly to the construction of the type.</span></span> <span data-ttu-id="4b77d-628">Библиотека [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) следует:</span><span class="sxs-lookup"><span data-stu-id="4b77d-628">[Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="4b77d-629">UnifiedJsonWriter.JsonTextWriter.cs</span><span class="sxs-lookup"><span data-stu-id="4b77d-629">UnifiedJsonWriter.JsonTextWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [<span data-ttu-id="4b77d-630">UnifiedJsonWriter.Utf8JsonWriter.cs</span><span class="sxs-lookup"><span data-stu-id="4b77d-630">UnifiedJsonWriter.Utf8JsonWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a><span data-ttu-id="4b77d-631">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="4b77d-631">Additional resources</span></span>

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* <span data-ttu-id="4b77d-632">[Обзор System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4b77d-632">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="4b77d-633">[Как использовать System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="4b77d-633">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* [<span data-ttu-id="4b77d-634">Практическое руководство. Написание настраиваемых преобразователей</span><span class="sxs-lookup"><span data-stu-id="4b77d-634">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="4b77d-635">[Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="4b77d-635">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="4b77d-636">[Справочник по API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="4b77d-636">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="4b77d-637">[Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="4b77d-637">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
