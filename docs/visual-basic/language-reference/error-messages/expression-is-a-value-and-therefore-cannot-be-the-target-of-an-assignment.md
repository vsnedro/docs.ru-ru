---
title: Нельзя присвоить значение выражению, поскольку оно является значением
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 9e4dbaf2f2800454c673cd58ddec4cf0f6e5c6b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409512"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>Нельзя присвоить значение выражению, поскольку оно является значением

Оператор пытается присвоить значение выражению. Значение можно назначить только переменной с возможностью записи, свойству или элементу массива во время выполнения. В следующем примере показано, как может произойти эта ошибка.

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

Аналогичные примеры могут применяться к свойствам и элементам массива.

**Косвенный доступ.** Непрямой доступ через тип значения может также вызвать эту ошибку. Рассмотрим следующий пример кода, который пытается задать значение <xref:System.Drawing.Point> путем прямого доступа к нему через <xref:System.Windows.Forms.Control.Location%2A> .

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

Последняя инструкция из предыдущего примера завершается сбоем, так как создает только временное выделение для <xref:System.Drawing.Point> структуры, возвращаемой <xref:System.Windows.Forms.Control.Location%2A> свойством. Структура является типом значения, а временная структура не сохраняется после выполнения инструкции. Проблема решается путем объявления и использования переменной для <xref:System.Windows.Forms.Control.Location%2A> , которая создает более постоянное выделение для <xref:System.Drawing.Point> структуры. В следующем примере показан код, который может заменить последнюю инструкцию из предыдущего примера.

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

**Идентификатор ошибки:** BC30068

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если оператор присваивает значение выражению, замените выражение одной записываемой переменной, свойством или элементом массива.

- Если инструкция делает косвенный доступ через тип значения (обычно это структура), создайте переменную для хранения типа значения.

- Назначьте переменной соответствующую структуру (или другой тип значения).

- Используйте переменную для доступа к свойству, чтобы присвоить ему значение.

## <a name="see-also"></a>См. также раздел

- [Операторы и выражения](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Операторы](../../programming-guide/language-features/statements.md)
- [Рекомендации по устранению неполадок](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
