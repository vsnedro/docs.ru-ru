---
ms.openlocfilehash: 97fab784acac4331894547eea27fc21b485597fb
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366866"
---
### <a name="passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation"></a>Передача GroupCollection в методы расширения, принимающие IEnumerable\<T>, требует устранения неоднозначности

При вызове метода расширения, который принимает `IEnumerable<T>` в <xref:System.Text.RegularExpressions.GroupCollection>, необходимо устранить неоднозначность типа с помощью приведения.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Core 3.0 <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> реализует `IEnumerable<KeyValuePair<String,Group>>` в дополнение к другим реализуемым типам, включая `IEnumerable<Group>`. Это приводит к неоднозначности при вызове метода расширения, который принимает <xref:System.Collections.Generic.IEnumerable%601>. При вызове такого метода расширения в экземпляре <xref:System.Text.RegularExpressions.GroupCollection>, например <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, вы увидите следующую ошибку компилятора:

**CS1061: "GroupCollection" не содержит определение для "Count", и не удается найти метод расширения "Count", принимающий первый аргумент типа "GroupCollection" (возможно, пропущена директива using или ссылка на сборку)**

В предыдущих версиях .NET не существовало неоднозначности и не было таких ошибок компилятора.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

Это было [непреднамеренное критическое изменение](https://github.com/dotnet/corefx/pull/30077). Так как все это уже существовало некоторое время, мы не планируем отменять его. Кроме того, такое изменение само по себе будет критическим.

#### <a name="recommended-action"></a>Рекомендованное действие

Для экземпляров <xref:System.Text.RegularExpressions.GroupCollection> устраните неоднозначность вызовов методов расширения, которые принимают `IEnumerable<T>`, путем приведения.

```csharp
// Without a cast - causes CS1061.
match.Groups.Count(_ => true)

// With a disambiguating cast.
((IEnumerable<Group>)m.Groups).Count(_ => true);
```

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

Затрагиваются все методы расширения, принимающие <xref:System.Collections.Generic.IEnumerable%601>. Пример:

- <xref:System.Collections.Immutable.ImmutableArray.ToImmutableArray%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableList.ToImmutableList%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet%2A?displayProperty=fullName>
- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A?displayProperty=fullName>
- Большинство методов `System.Linq.Enumerable`, например <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName>
- <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=fullName>
- <xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>

<!--

#### Affected APIs

- ``M:System.Collections.Immutable.ImmutableArray.ToImmutableArray``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary`
- `Overload:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet`
- ``M:System.Collections.Immutable.ImmutableList.ToImmutableList``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary`
- `Overload:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet`
- `Overload:System.Data.DataTableExtensions.CopyToDataTable`
- `Overload:System.Linq.Enumerable.Count`
- `Overload:System.Linq.ParallelEnumerable.AsParallel`
- `Overload:System.Linq.Queryable.AsQueryable`

-->
