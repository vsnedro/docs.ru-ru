---
ms.openlocfilehash: e128bdb5735b3e4844356ad4807cc092f6f2b105
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062433"
---
### <a name="no-aw-suffix-probing-on-non-windows-platforms"></a>Отсутствует проверка суффикса A/W на платформах, отличных от Windows

Среды выполнения .NET больше не добавляют суффиксы `A` или `W` к именам экспортируемых функций во время проверки для P/Invokes на платформах, отличных от Windows.

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 4

#### <a name="change-description"></a>Описание изменений

[По соглашению Windows](/windows/win32/intl/conventions-for-function-prototypes), к именам функций Windows SDK, которые соответствуют кодовой странице Windows и версиям Юникода, добавляются суффиксы `A` и `W` соответственно.

В предыдущих версиях .NET в средах выполнения CoreCLR и Mono к именам экспорта добавлялись суффиксы `A` или `W` во время обнаружения экспорта для P/Invokes *на всех платформах*.

В .NET 5.0 и более поздней версии суффиксы `A` или `W` добавляется к именам экспорта во время обнаружения экспорта *только в Windows*. На платформах UNIX суффикс не добавляется. Семантика обеих сред выполнения на платформе Windows остается неизменной.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение было внесено с целью упрощения проверки на нескольких платформах. Это изменение не должно привести к дополнительным издержкам, так как платформы, отличные от Windows, не содержат такой семантики.

#### <a name="recommended-action"></a>Рекомендованное действие

Чтобы ослабить эффект этого изменения, можно вручную добавить требуемый суффикс на платформах, отличных от Windows. Пример:

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

#### <a name="category"></a>Категория

Interop

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

-->
