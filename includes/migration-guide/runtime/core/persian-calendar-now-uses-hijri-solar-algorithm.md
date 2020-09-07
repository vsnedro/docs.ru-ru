---
ms.openlocfilehash: 14581b193fc000c7f805a0602e191cad688c014a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496424"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>Теперь в персидском календаре используется алгоритм солнечного календаря хиджры

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6 класс <xref:System.Globalization.PersianCalendar?displayProperty=fullName> использует алгоритм солнечного календаря хиджры. Начиная с .NET Framework 4.6 при преобразовании дат между <xref:System.Globalization.PersianCalendar?displayProperty=fullName> и другими календарями может быть получен немного другой результат для дат, ранее 1800 г. или позднее 2023 г. (по григорианскому календарю). Кроме того, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> теперь <code>March 22, 0622</code> вместо <code>March 21, 0622</code>.

#### <a name="suggestion"></a>Предложение

Имейте в виду, что при использовании персидского календаря в .NET Framework 4.6 некоторые даты в прошлом или будущем могут несколько отличаться. Кроме того, даты, сериализуемые между процессами, которые могут выполняться в различных версиях .NET Framework, не следует хранить в виде строк дат персидского календаря (поскольку эти значения могут быть разными).

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Globalization.PersianCalendar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Globalization.PersianCalendar`

-->
