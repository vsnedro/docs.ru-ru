---
title: Рекомендации по отображению и сохранению форматированных данных в .NET
description: Узнайте, как эффективно отображать и сохранять числовые данные и даты в приложениях .NET.
ms.date: 05/01/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1748363089a80538a19e91b1955fe9257de39a4e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825147"
---
# <a name="best-practices-for-displaying-and-persisting-formatted-data"></a>Рекомендации по отображению и сохранению форматированных данных

Кроме того, в этой статье рассматривается отображение и хранение форматированных данных, например числовых данных или даты и времени.

При разработке с помощью .NET используйте форматирование с учетом языка и региональных параметров для отображения нестроковых данных, например чисел и дат, в пользовательском интерфейсе. Для сохранения нестроковых данных в строковой форме используйте форматирование [инвариантного языка и региональных параметров](xref:System.Globalization.CultureInfo.InvariantCulture). Не используйте форматирование с учетом языка и региональных параметров для сохранения числовых данных или данных даты и времени в виде строки.

## <a name="displaying-formatted-data"></a>Отображение форматированных данных

При отображении нестроковых данных, например чисел, дат и времени, пользователям следует форматировать их с использованием параметров языка и региональных параметров пользователя. По умолчанию все следующие объекты используют текущий язык и региональные параметры потока в операциях форматирования:

- Интерполированные строки, поддерживаемые компиляторами [C#](../../csharp/language-reference/tokens/interpolated.md) и [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md).
- Строковые операции объединения, использующие операторы объединения [C#](../../csharp/language-reference/operators/addition-operator.md#string-concatenation) или [Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) или вызывающие метод <xref:System.String.Concat%2A?displayProperty=nameWithType> напрямую.
- метод <xref:System.String.Format%2A?displayProperty=nameWithType> ;
- Методы `ToString` числовых типов, а также типы даты и времени.

Чтобы явно указать, что строка должна форматироваться с помощью правил заданного языка и региональных параметров или [инвариантного языка и региональных параметров](xref:System.Globalization.CultureInfo.InvariantCulture), можно сделать следующее:

- При использовании методов <xref:System.String.Format%2A?displayProperty=nameWithType> и `ToString` вызовите перегрузку с параметром `provider`, например <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> или <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType>, и передайте ему свойство <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>, экземпляр <xref:System.Globalization.CultureInfo>, представляющий требуемый язык и региональные параметры, или свойство <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.

- Для объединения строк не позволяйте компилятору выполнять неявные преобразования. Вместо этого выполните явное преобразование путем вызова перегрузки `ToString` с параметром `provider`. Например, компилятор неявно использует текущий язык и региональные параметры при преобразовании значения <xref:System.Double> в строку в следующем коде:

  [!code-csharp[Implicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#1)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#1)]

  Вместо этого можно явно указать язык и региональные параметры, соглашения о форматировании которых используются в преобразовании, вызвав метод <xref:System.Double.ToString(System.IFormatProvider)?displayProperty=nameWithType>, как показано в следующем коде:

  [!code-csharp[Explicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#2)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#2)]

- Для интерполяции строк вместо назначения интерполированной строки экземпляру <xref:System.String> назначьте его <xref:System.FormattableString>. Затем можно вызвать его метод <xref:System.FormattableString.ToString?displayProperty=nameWithType>, чтобы создать результирующую строку, отражающую правила для текущего языка и региональных параметров, либо можно вызвать метод <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType>, чтобы создать результирующую строку, отражающую правила для указанного языка и региональных параметров. Также можно передать форматируемую строку статическому методу <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType>, чтобы создать результирующую строку, отражающую правила для инвариантного языка и региональных параметров. Этот подход показан в приведенном ниже примере. (Выходные данные примера отражают текущий язык и региональные параметры en-US.)

  [!code-csharp[String interpolation](./snippets/best-practices-strings/csharp/formattable/Program.cs)]
  [!code-vb[String interpolation](./snippets/best-practices-strings/vb/formattable/Program.vb)]

## <a name="persisting-formatted-data"></a>Сохранение форматированных данных

Нестроковые данные можно сохранить в виде двоичных или форматированных данных. Если решено сохранять данные в виде форматированных, нужно вызвать перегрузку метода форматирования, которая включает параметр `provider` , и передать ей свойство <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> . Инвариантный язык и региональные параметры предоставляют согласованный формат для форматированных данных независимо от языка, региональных параметров и компьютера. Напротив, сохранение форматированных данных с использованием языков и региональных параметров, отличающихся от инвариантных, имеет ряд ограничений.

- Данные, вероятно, станут недоступными для использования после извлечения в системе с другим языком либо если пользователь текущей системы сменит текущий язык и попытается извлечь данные.
- Свойства языка и региональных параметров на конкретном компьютере могут отличаться от стандартных значений. Пользователь может в любой момент настроить параметры отображения с учетом языка и региональных параметров. По этой причине форматированные данные, которые сохраняются в системе, могут стать недоступными для чтения после изменения настроек языка пользователем. Переносимость форматированных данных с одного компьютера на другой, вероятно, будет еще более ограниченной.
- Международные, региональные и национальные стандарты, регулирующие форматирование чисел, дат и времени, со временем меняются, и эти изменения отражаются в обновлениях ОС Windows. При изменении правил форматирования данные, форматированные с использованием старых правил, становятся недоступными для чтения.

В следующем примере демонстрируется ограниченная переносимость в результате использования для сохранения данных форматирования с учетом языка и региональных параметров. В этом примере массив значений даты и времени сохраняется в файл. Данные форматируются с использованием правил английского языка (США). После того как приложение сменит текущий язык потока на французский (Швейцария), оно попытается прочитать сохраненные значения, используя правила форматирования текущей культуры. При попытке чтения двух элементов данных создается исключение <xref:System.FormatException> , а массив дат теперь содержит два неправильных элемента, равных <xref:System.DateTime.MinValue>.

[!code-csharp[Conceptual.Strings.BestPractices#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/persistence.cs#21)]
[!code-vb[Conceptual.Strings.BestPractices#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/persistence.vb#21)]

Но если изменить свойство <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> на <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> в вызовах методов <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> и <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, хранимые данные даты и времени будут восстановлены успешно, как показано ниже.

```console
06.05.1758 21:26
05.05.1818 07:19
22.04.1870 23:54
08.09.1890 06:47
18.02.1905 15:12
```
