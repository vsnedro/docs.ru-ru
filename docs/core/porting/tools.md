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
# <a name="tools-to-help-with-porting-to-net-core"></a>Инструменты для переноса в .NET Core

Инструменты в этой статье помогут вам при переносе:

- [Анализатор переносимости .NET](../../standard/analyzers/portability-analyzer.md) — цепочка инструментов, создающих отчеты о переносимости кода между .NET Framework и .NET Core:
  - как [программа командной строки](https://github.com/Microsoft/dotnet-apiport/releases);
  - как [расширение Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).
- [Анализатор совместимости платформ.](../../standard/analyzers/platform-compat-analyzer.md) Анализатор Roslyn, который информирует разработчиков об использовании интерфейсов API для конкретных платформ с сайтов вызовов, где API может быть недоступен.
- [Анализатор API .NET.](../../standard/analyzers/api-analyzer.md) Анализатор Roslyn, который помогает определять проблемы совместимости платформ в кросс-платформенных приложениях и библиотеках.
- [try-convert](https://www.nuget.org/packages/try-convert/) — глобальное средство .NET Core, которое может преобразовать проект или все решение в пакет SDK для .NET, включая перенос настольных приложений в .NET Core. Это не рекомендуется, если у вас более сложная сборка (например, пользовательские задачи, целевые объекты или импорты), так как будут отклоняться многие типы проектов, несовместимые с .NET Core.
