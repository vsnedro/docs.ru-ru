---
title: Критическое изменение. В RC2 изменились имена параметров
description: Ознакомьтесь с критическим изменением .NET 5.0 в основных библиотеках .NET, где некоторые имена параметров ссылочных сборок изменились с версий .NET 5.0, выпущенных в виде предварительной версии и версии-кандидата.
ms.date: 11/01/2020
ms.openlocfilehash: 554a4fa9e08fdb504f380465496d7e7e9df85814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759754"
---
# <a name="parameter-names-changed-in-rc2"></a>В RC2 изменились имена параметров

Некоторые имена параметров ссылочных сборок изменились для соответствия с именами параметров в сборках реализации.

## <a name="change-description"></a>Описание изменений

В предыдущей предварительной версии и версии RC .NET 5.0 некоторые имена параметров [ссылочных сборок](../../../../standard/assembly/reference-assemblies.md) отличаются от соответствующих им параметров в сборке реализации. Это может вызвать проблемы при использовании именованных аргументов и отражения.

В .NET 5.0 RC2 несоответствующие имена параметров были изменены в ссылочных сборках, чтобы точно соответствовать именам параметров в сборках реализации.

В следующей таблице приведены измененные API-интерфейсы и имена параметров.

| API | Старое имя параметра | Новое имя параметра |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

## <a name="reason-for-change"></a>Причина изменения

Имена параметров были изменены для согласованности и предотвращения сбоев при использовании именованных аргументов и отражения.

## <a name="version-introduced"></a>Представленная версия

5.0 RC2

## <a name="recommended-action"></a>Рекомендованное действие

Если возникла ошибка компилятора из-за изменения имени параметра, измените имя параметра соответствующим образом.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
