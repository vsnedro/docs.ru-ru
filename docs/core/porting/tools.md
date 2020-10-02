---
title: Инструменты для переноса в .NET Core
description: Дополнительные сведения о некоторых инструментах, которые можно использовать для переноса в .NET Core
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406132"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="e555b-103">Инструменты для переноса в .NET Core</span><span class="sxs-lookup"><span data-stu-id="e555b-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="e555b-104">Инструменты в этой статье помогут вам при переносе:</span><span class="sxs-lookup"><span data-stu-id="e555b-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="e555b-105">[Анализатор переносимости .NET](../../standard/analyzers/portability-analyzer.md) — цепочка инструментов, создающих отчеты о переносимости кода между .NET Framework и .NET Core:</span><span class="sxs-lookup"><span data-stu-id="e555b-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="e555b-106">как [программа командной строки](https://github.com/Microsoft/dotnet-apiport/releases);</span><span class="sxs-lookup"><span data-stu-id="e555b-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="e555b-107">как [расширение Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).</span><span class="sxs-lookup"><span data-stu-id="e555b-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="e555b-108">[Анализатор совместимости платформ.](../../standard/analyzers/platform-compat-analyzer.md) Анализатор Roslyn, который информирует разработчиков об использовании интерфейсов API для конкретных платформ с сайтов вызовов, где API может быть недоступен.</span><span class="sxs-lookup"><span data-stu-id="e555b-108">[Platform compatibility analyzer](../../standard/analyzers/platform-compat-analyzer.md) - A Roslyn analyzer that informs developers when they use platform-specific APIs from call sites where the API might not be available.</span></span>
- <span data-ttu-id="e555b-109">[Анализатор API .NET.](../../standard/analyzers/api-analyzer.md) Анализатор Roslyn, который помогает определять проблемы совместимости платформ в кросс-платформенных приложениях и библиотеках.</span><span class="sxs-lookup"><span data-stu-id="e555b-109">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that can help detect platform compatibility issues in cross-platform apps and libraries.</span></span>
- <span data-ttu-id="e555b-110">[try-convert](https://www.nuget.org/packages/try-convert/) — глобальное средство .NET Core, которое может преобразовать проект или все решение в пакет SDK для .NET, включая перенос настольных приложений в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e555b-110">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="e555b-111">Это не рекомендуется, если у вас более сложная сборка (например, пользовательские задачи, целевые объекты или импорты), так как будут отклоняться многие типы проектов, несовместимые с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e555b-111">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
