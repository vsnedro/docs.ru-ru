---
description: 'Дополнительные сведения: Shared (Visual Basic)'
title: Shared
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 0cc671c67486d01026f2283837448db7b00c1a0a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700758"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)

Указывает, что один или несколько объявленных программных элементов связаны с классом или структурой в большом объеме, а не с конкретным экземпляром класса или структуры.

## <a name="when-to-use-shared"></a>Когда следует использовать Shared

Совместное использование члена класса или структуры делает его доступным для каждого экземпляра, а не для *общего доступа*, где каждый экземпляр хранит собственную копию. Общий доступ может быть полезен, например, если значение переменной применяется ко всему приложению. Если объявить эту переменную как `Shared` , то все экземпляры получают доступ к тому же месту хранения, и если один экземпляр изменяет значение переменной, все экземпляры получают доступ к обновленному значению.

Совместное использование не изменяет уровень доступа элемента. Например, член класса может быть общим и частным (доступным только в пределах класса), а также не является общим и открытым. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Правила

- **Контекст объявления.** `Shared` можно использовать только на уровне модуля. Это означает, что контекст объявления для `Shared` элемента должен быть классом или структурой и не может быть исходным файлом, пространством имен или процедурой.

- **Комбинированные модификаторы.** Нельзя указывать `Shared` вместе с [переопределениями](overrides.md), [переопределяемыми](overridable.md), [NotOverridable](notoverridable.md), [MustOverride](mustoverride.md)или [static](static.md) в одном объявлении.

- **Данному.** Доступ к общему элементу осуществляется путем указания его имени класса или структуры, а не имени переменной определенного экземпляра его класса или структуры. Вам даже не нужно создавать экземпляр класса или структуры для доступа к его общим членам.

     В следующем примере вызывается общая процедура, <xref:System.Double.IsNaN%2A> предоставляемая <xref:System.Double> структурой.

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- **Неявный общий доступ.** Нельзя использовать `Shared` Модификатор в [операторе const](../statements/const-statement.md), но константы неявно являются общими. Аналогичным образом нельзя объявить член модуля или интерфейса `Shared` , но они являются неявно общими.

## <a name="behavior"></a>Поведение

- **Объема.** Общая переменная или событие хранится в памяти только один раз, независимо от того, сколько экземпляров вы создаете его класс или структуру. Аналогично, Общая процедура или свойство содержит только один набор локальных переменных.

- **Доступ через переменную экземпляра.** Доступ к общему элементу можно получить, добавив в него имя переменной, содержащей конкретный экземпляр его класса или структуры. Несмотря на то, что обычно работает, как и ожидалось, компилятор создает предупреждающее сообщение и предоставляет доступ через имя класса или структуры вместо переменной.

- **Доступ через выражение экземпляра.** При доступе к общему элементу с помощью выражения, возвращающего экземпляр класса или структуры, компилятор делает доступ через имя класса или структуры вместо вычисления выражения. Такой доступ дает непредвиденные результаты, если выражение предназначено для выполнения других действий, а также для возврата экземпляра. В следующем примере показана такая ситуация.
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     В предыдущем примере компилятор выдает предупреждающее сообщение в обоих случаях, когда код обращается к общему свойству `Total` через экземпляр. В каждом случае он делает доступ напрямую через класс `ShareTotal` и не использует ни одного экземпляра. В случае предполагаемого вызова процедуры `ReturnClass` это означает, что он даже не создает вызов `ReturnClass` , поэтому не выполняется дополнительное действие отображения "функция ретурнкласс ()".

Модификатор `Shared` можно использовать в следующих контекстах:

- [Оператор Dim](../statements/dim-statement.md)
- [Оператор Event](../statements/event-statement.md)
- [Оператор Function](../statements/function-statement.md)
- [Operator Statement](../statements/operator-statement.md)
- [Property Statement](../statements/property-statement.md)
- [Оператор Sub](../statements/sub-statement.md)
  
## <a name="see-also"></a>См. также

- [Shadows](shadows.md)
- [статически.](static.md)
- [Время существования в Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
