---
title: Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: e16a157d0621d5baecb06ce118e3ab390bf68cf8
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162886"
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
