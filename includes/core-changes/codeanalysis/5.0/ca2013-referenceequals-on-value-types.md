---
ms.openlocfilehash: b01424c63d6e7956127bf889c53422b60ba2f219
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065210"
---
### <a name="ca2013-do-not-use-referenceequals-with-value-types"></a>CA2013: не используйте ReferenceEquals с типами значений

Правило [CA2013](/visualstudio/code-quality/ca2013) анализатора кода .NET включено по умолчанию начиная с .NET 5.0. Оно создает предупреждение сборки для любого кода, где для сравнения одного или нескольких типов значений на предмет равенства используется <xref:System.Object.ReferenceEquals(System.Object,System.Object)>.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Некоторые из этих правил включены по умолчанию, в том числе [CA2013](/visualstudio/code-quality/ca2013). Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.

Правило CA2013 находит экземпляры, где для сравнения одного или нескольких типов значений на предмет равенства используется <xref:System.Object.ReferenceEquals(System.Object,System.Object)>. Сравнение типов значений на предмет равенства таким образом может привести к неверным результатам, так как значения упаковываются до их сравнения. <xref:System.Object.ReferenceEquals(System.Object,System.Object)> будет возвращать `false` даже в том случае, если сравниваемые значения представляют один и тот же экземпляр типа значения.

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="recommended-action"></a>Рекомендованное действие

- Измените код, чтобы использовать соответствующий оператор равенства, например `==`. Не следует отключать это предупреждение.

- Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта. Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Категория

Анализ кода

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

-->
