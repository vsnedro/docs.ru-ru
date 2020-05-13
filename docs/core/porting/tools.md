---
title: Инструменты для переноса в .NET Core
description: Дополнительные сведения о некоторых инструментах, которые можно использовать для переноса в .NET Core
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: d0cf0abf206950beb34556ca3ba7243d8cad241e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795590"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="e02bd-103">Инструменты для переноса в .NET Core</span><span class="sxs-lookup"><span data-stu-id="e02bd-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="e02bd-104">Инструменты в этой статье помогут вам при переносе:</span><span class="sxs-lookup"><span data-stu-id="e02bd-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="e02bd-105">[Анализатор переносимости .NET](../../standard/analyzers/portability-analyzer.md) — цепочка инструментов, создающих отчеты о переносимости кода между .NET Framework и .NET Core:</span><span class="sxs-lookup"><span data-stu-id="e02bd-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="e02bd-106">как [программа командной строки](https://github.com/Microsoft/dotnet-apiport/releases);</span><span class="sxs-lookup"><span data-stu-id="e02bd-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="e02bd-107">как [расширение Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).</span><span class="sxs-lookup"><span data-stu-id="e02bd-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="e02bd-108">[Анализатор API .NET](../../standard/analyzers/api-analyzer.md) — анализатор на основе Roslyn выявляет риски совместимости для API на языке C# на разных платформах, а также отслеживает вызовы устаревших API.</span><span class="sxs-lookup"><span data-stu-id="e02bd-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>
- <span data-ttu-id="e02bd-109">[try-convert](https://www.nuget.org/packages/try-convert/) — глобальное средство .NET Core, которое может преобразовать проект или все решение в пакет SDK для .NET, включая перенос настольных приложений в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e02bd-109">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="e02bd-110">Это не рекомендуется, если у вас более сложная сборка (например, пользовательские задачи, целевые объекты или импорты), так как будут отклоняться многие типы проектов, несовместимые с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e02bd-110">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
