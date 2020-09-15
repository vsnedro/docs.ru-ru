---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065183"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a>CA2014: не используйте stackalloc в циклах

Правило [CA2014](/visualstudio/code-quality/ca2014) анализатора кода .NET включено по умолчанию, начиная с .NET 5.0. Оно создает предупреждение сборки для любого кода C#, в котором используется выражение [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) внутри цикла.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Некоторые из этих правил включены по умолчанию, в том числе [CA2014](/visualstudio/code-quality/ca2014). Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.

Правило CA2014 ищет код C#, в котором выражение [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) используется внутри цикла. [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) выделяет память из текущего кадра стека. Память не освобождается до тех пор, пока не будет возвращен текущий вызов метода, что может привести к переполнению стека. Так как вы не можете перехватывать исключения переполнения стека, в таком случае работа приложения будет завершена.

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="recommended-action"></a>Рекомендованное действие

- Старайтесь не использовать [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) в циклах. Выделяйте блок памяти за пределами цикла и используйте его повторно внутри цикла. См. раздел [CA2014](/visualstudio/code-quality/ca2014).

- Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта. Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Категория

Анализ кода

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
