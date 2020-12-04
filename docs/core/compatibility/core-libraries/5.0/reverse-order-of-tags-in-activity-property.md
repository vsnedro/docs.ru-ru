---
title: Критическое изменение. Порядок тегов в действии Activity.Tags обращен
description: Сведения о критическом изменении в .NET 5.0 в основных библиотеках .NET, где Activity.Tags теперь сохраняет элементы в списке в соответствии с порядком их добавления.
ms.date: 11/01/2020
ms.openlocfilehash: 1ff14dc1a4f7a0bf8cf9e79f3750b819f4d4a5ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759749"
---
# <a name="order-of-tags-in-activitytags-is-reversed"></a>Порядок тегов в действии Activity.Tags обращен

<xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> теперь сохраняет элементы в списке в соответствии с порядком их добавления, то есть первый добавленный элемент отображается в списке первым. Это изменение было внесено в соответствии со [спецификацией атрибутов OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> сохраняет элементы в порядке, обратном их добавлению. Это значит, что первый добавленный элемент является последним в списке. Начиная с .NET 5.0 порядок элементов теперь обратный, и первый добавленный элемент всегда находится в списке первым.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="recommended-action"></a>Рекомендованное действие

Если приложение зависит от порядка элементов в списке <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> и выполняется обновление до .NET 5.0 или более поздней версии, необходимо изменить эту часть кода.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
