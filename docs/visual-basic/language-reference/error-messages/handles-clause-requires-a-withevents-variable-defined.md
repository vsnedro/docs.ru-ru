---
description: 'Дополнительные сведения о: BC30506: Handles требуется переменная с модификатором WithEvents, определенная в содержащем типе или в одном из его базовых типов'
title: Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 7253a4766b2015ccbe0ae62f64bc10aaca073dc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796123"
---
# <a name="bc30506-handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>Для предложения BC30506: Handles требуется переменная с модификатором WithEvents, определенная в содержащем типе или в одном из его базовых типов

Вы не указали `WithEvents` переменную в `Handles` предложении. `Handles`Ключевое слово в конце объявления процедуры вызывает обработку событий, вызванных переменной объекта, объявленной с помощью `WithEvents` ключевого слова.

**Идентификатор ошибки:** BC30506

## <a name="to-correct-this-error"></a>Исправление ошибки

Укажите необходимую `WithEvents` переменную.

## <a name="example"></a>Пример

В следующем примере Visual Basic создает ошибку компилятора, `BC30506` так как ключевое слово [WithEvents](../modifiers/withevents.md) не используется в определении <xref:System.Timers.Timer?displayProperty=nameWithType> экземпляра.

```vb
Imports System.Timers

Module Module1
    Private _timer1 As New Timer() With {.Interval = 1000, .Enabled = True}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub
End Module
```

Следующий пример компилируется успешно, так как `_timer1` переменная определена с помощью `WithEvents` ключевого слова:

```vb
Imports System.Timers

Module Module1
    Private WithEvents _timer1 As New Timer() With {.Interval = 1000}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub

End Module
```

## <a name="see-also"></a>См. также

- [Маркеры](../statements/handles-clause.md)
