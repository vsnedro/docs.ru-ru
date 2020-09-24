---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738828"
---
### <a name="parameter-names-changed-in-rc1"></a>В RC1 изменились имена параметров

Некоторые имена параметров ссылочных сборок изменились для соответствия с именами параметров в сборках реализации.

#### <a name="change-description"></a>Описание изменений

В предыдущей предварительной версии и версии RC .NET 5.0 некоторые имена параметров [ссылочных сборок](../../../../docs/standard/assembly/reference-assemblies.md) отличаются от соответствующих им параметров в сборке реализации. Это может вызвать проблемы при использовании именованных аргументов и отражения.

В .NET 5.0 RC2 несоответствующие имена параметров были изменены в ссылочных сборках, чтобы точно соответствовать именам параметров в сборках реализации.

В следующей таблице приведены измененные API-интерфейсы и имена параметров.

| API | Старое имя параметра | Новое имя параметра |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a>Причина изменения

Имена параметров были изменены для согласованности и предотвращения сбоев при использовании именованных аргументов и отражения.

#### <a name="version-introduced"></a>Представленная версия

5.0 RC2

#### <a name="recommended-action"></a>Рекомендованное действие

Если возникла ошибка компилятора из-за изменения имени параметра, измените имя параметра соответствующим образом.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
