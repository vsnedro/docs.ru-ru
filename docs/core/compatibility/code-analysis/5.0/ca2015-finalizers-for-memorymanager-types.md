---
title: 'Критическое изменение. CA2015: не определяйте методы завершения для типов, производных от MemoryManager<T>'
description: Сведения о критическом изменении в .NET 5.0, вызванном включением правила анализа кода CA2015.
ms.date: 09/03/2020
ms.openlocfilehash: 5d0ba0546b5a72363559f23713c8af4bb4e26e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759577"
---
# <a name="warning-ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a>Предупреждение CA2015: не определяйте методы завершения для типов, производных от MemoryManager\<T>

Правило [CA2015](/visualstudio/code-quality/ca2015) анализатора кода .NET включено по умолчанию, начиная с .NET 5.0. Оно создает предупреждение сборки для всех типов, производных от <xref:System.Buffers.MemoryManager%601>, определяющих метод завершения.

## <a name="change-description"></a>Описание изменений

Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../fundamentals/code-analysis/overview.md). Некоторые из этих правил включены по умолчанию, в том числе [CA2015](/visualstudio/code-quality/ca2015). Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.

Правило CA2015 помечает типы, производные от <xref:System.Buffers.MemoryManager%601>, которые определяют метод завершения. Добавление метода завершения в тип, производный от <xref:System.Buffers.MemoryManager%601>, скорее всего, свидетельствует об ошибке. Предполагается, что собственный ресурс, который мог быть получен в <xref:System.Span%601>, очищается, даже если он по-прежнему используется <xref:System.Span%601>.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="recommended-action"></a>Рекомендованное действие

- Удалите определение метода завершения. См. раздел [CA2015](/visualstudio/code-quality/ca2015).

- Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта. Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
