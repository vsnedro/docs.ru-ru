---
title: Критические изменения анализа кода
description: Список критических изменений в анализаторах исходного кода .NET.
ms.date: 08/22/2020
ms.openlocfilehash: 8b2b50c5f03a3ca971aefd0f2cf53624dfa82274
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465593"
---
# <a name="code-analysis-breaking-changes"></a>Критические изменения анализа кода

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [CA1831: используйте AsSpan или AsMemory вместо индексаторов на основе диапазонов](#ca1831-use-asspan-or-asmemory-instead-of-range-based-indexer) | 5.0 |
| [CA2014: не используйте stackalloc в циклах](#ca2014-do-not-use-stackalloc-in-loops) | 5.0 |
| [CA2015: не определяйте методы завершения для типов, производных от MemoryManager\<T>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | 5.0 |
| [CA2247: аргумент для конструктора TaskCompletionSource должен соответствовать значению TaskCreationOptions](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/range-based-indexer-on-string.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ctor-arg-should-be-taskcreationoptions.md)]

***
