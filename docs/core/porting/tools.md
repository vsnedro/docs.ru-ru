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
# <a name="tools-to-help-with-porting-to-net-core"></a>Инструменты для переноса в .NET Core

Инструменты в этой статье помогут вам при переносе:

- [Анализатор переносимости .NET](../../standard/analyzers/portability-analyzer.md) — цепочка инструментов, создающих отчеты о переносимости кода между .NET Framework и .NET Core:
  - как [программа командной строки](https://github.com/Microsoft/dotnet-apiport/releases);
  - как [расширение Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).
- [Анализатор API .NET](../../standard/analyzers/api-analyzer.md) — анализатор на основе Roslyn выявляет риски совместимости для API на языке C# на разных платформах, а также отслеживает вызовы устаревших API.
- [try-convert](https://www.nuget.org/packages/try-convert/) — глобальное средство .NET Core, которое может преобразовать проект или все решение в пакет SDK для .NET, включая перенос настольных приложений в .NET Core. Это не рекомендуется, если у вас более сложная сборка (например, пользовательские задачи, целевые объекты или импорты), так как будут отклоняться многие типы проектов, несовместимые с .NET Core.
