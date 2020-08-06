---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302724"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a>Vector\<T> всегда вызывает исключение NotSupportedException для неподдерживаемых типов

<xref:System.Numerics.Vector%601?displayProperty=nameWithType> теперь всегда вызывает <xref:System.NotSupportedException> для неподдерживаемых параметров типа.

#### <a name="change-description"></a>Описание изменений

Ранее члены <xref:System.Numerics.Vector%601> не всегда вызывали <xref:System.NotSupportedException>, если у `T` был [неподдерживаемый тип](#unsupported-types). Исключение не всегда вызывалось из-за путей к коду, поддерживающих аппаратное ускорение. Например, для `Vector<bool> + Vector<bool>` возвращалось `default` вместо вызова исключения на платформах без аппаратного ускорения, например ARM32. Для неподдерживаемых типов члены <xref:System.Numerics.Vector%601> демонстрируют несогласованное поведение на разных платформах и с разными конфигурациями оборудования.

Начиная с .NET 5.0, члены <xref:System.Numerics.Vector%601> всегда вызывают <xref:System.NotSupportedException> во всех конфигурациях оборудования, если `T` не является поддерживаемым типом.

##### <a name="unsupported-types"></a>Неподдерживаемые типы

Поддерживаемые типы для параметра типа <xref:System.Numerics.Vector%601>:

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

Поддерживаемые типы не изменились, но могут измениться в будущем.

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="recommended-action"></a>Рекомендованное действие

Не используйте неподдерживаемый тип для параметра типа <xref:System.Numerics.Vector%601>.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Numerics.Vector%601?displayProperty=fullName> и все связанные члены

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
