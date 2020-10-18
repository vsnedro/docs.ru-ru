---
title: Лямбда-выражение не будет удалено из этого обработчика событий
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 5a30e63044b51f8176dfeebdcc9eb8fd517739ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163120"
---
# <a name="bc42326-lambda-expression-will-not-be-removed-from-this-event-handler"></a>BC42326: лямбда-выражение не будет удалено из этого обработчика событий

Лямбда-выражение не будет удалено из этого обработчика событий. Назначьте лямбда-выражение переменной и используйте переменную для добавления и удаления события.

При использовании лямбда-выражений с обработчиками событий вы не сможете увидеть ожидаемое поведение. Компилятор создает новый метод для каждого определения лямбда-выражения, даже если они идентичны. Поэтому отображается следующий код `False` .

```vb
Module Module1

    Sub Main()
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1
        Console.WriteLine(fun1 = fun2)
    End Sub

    Delegate Function ChangeInteger(ByVal x As Integer) As Integer

End Module
```

При использовании лямбда-выражений с обработчиками событий это может привести к непредвиденным результатам. В следующем примере лямбда-выражение, добавленное с помощью, `AddHandler` не удаляется `RemoveHandler` инструкцией.

```vb
Module Module1

    Event ProcessInteger(ByVal x As Integer)

    Sub Main()

        ' The following line adds one listener to the event.
        AddHandler ProcessInteger, Function(m As Integer) m

        ' The following statement searches the current listeners
        ' for a match to remove. However, this lambda is not the same
        ' as the previous one, so nothing is removed.
        RemoveHandler ProcessInteger, Function(m As Integer) m

    End Sub
End Module
```

По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

**Идентификатор ошибки:** BC42326

## <a name="to-correct-this-error"></a>Исправление ошибки

Чтобы избежать предупреждения и удалить лямбда-выражение, назначьте лямбда-выражение переменной и используйте переменную в `AddHandler` `RemoveHandler` инструкциях и, как показано в следующем примере.

```vb
Module Module1

    Event ProcessInteger(ByVal x As Integer)

    Dim PrintHandler As ProcessIntegerEventHandler

    Sub Main()

        ' Assign the lambda expression to a variable.
        PrintHandler = Function(m As Integer) m

        ' Use the variable to add the listener.
        AddHandler ProcessInteger, PrintHandler

        ' Use the variable again when you want to remove the listener.
        RemoveHandler ProcessInteger, PrintHandler

    End Sub
End Module
```

## <a name="see-also"></a>См. также

- [Лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Неявное преобразование делегата](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [События](../../programming-guide/language-features/events/index.md)
