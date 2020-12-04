---
title: Критическое изменение. IntPtr и UIntPtr реализуют IFormattable
description: Ознакомьтесь с критическим изменением .NET 5.0 в основных библиотеках .NET, где IntPtr и UIntPtr теперь реализуют IFormattable.
ms.date: 11/01/2020
ms.openlocfilehash: 0684652cdc2b8cf1d237074263bf0809082b0dcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759955"
---
# <a name="intptr-and-uintptr-implement-iformattable"></a>IntPtr и UIntPtr реализуют IFormattable

<xref:System.IntPtr> и <xref:System.UIntPtr> теперь реализуют <xref:System.IFormattable>. Функции, которые проверяют наличие поддержки <xref:System.IFormattable>, теперь могут возвращать разные результаты для этих типов, поскольку они могут передавать описатель формата, а также язык и региональные параметры.

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET <xref:System.IntPtr> и <xref:System.UIntPtr> не реализуют <xref:System.IFormattable>. Функции, которые проверяют наличие поддержки <xref:System.IFormattable>, могут возвращаться к простому вызову <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> или <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, что означает, что описатели формата, а также языки и региональные параметры не учитываются.

В .NET 5.0 и более поздних версиях <xref:System.IntPtr> и <xref:System.UIntPtr> реализуют <xref:System.IFormattable>. Функции, которые проверяют наличие поддержки <xref:System.IFormattable>, теперь могут возвращать разные результаты для этих типов, поскольку они могут передавать описатель формата, а также язык и региональные параметры.

Это изменение влияет на такие сценарии, как интерполяция строк и <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>.

## <a name="reason-for-change"></a>Причина изменения

<xref:System.IntPtr> и <xref:System.UIntPtr> теперь имеют языковую поддержку в C# помощью ключевых слов `nint` и `nuint`. Резервные типы были обновлены для обеспечения ближайшей четности (по возможности) с функциями, предоставляемыми другими примитивными типами, такими как <xref:System.Int32?displayProperty=nameWithType>.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="recommended-action"></a>Рекомендованное действие

Если вы не хотите использовать описатель формата или настраиваемые язык и региональные параметры при отображении значений этих типов, можно вызвать перегрузки <xref:System.IntPtr.ToString?displayProperty=nameWithType> и <xref:System.UIntPtr.ToString?displayProperty=nameWithType> для `ToString()`.

## <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

### Category

Core .NET libraries

### Affected APIs

Not detectable via API analysis.

-->
