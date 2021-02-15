---
description: Дополнительные сведения см. в статье как вызвать метод расширения (Visual Basic).
title: Практическое руководство. Вызов метода расширения
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: ec5217526eb0cb28d172ab917df08a8bfe87fe95
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471387"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Практическое руководство. Вызов метода расширения (Visual Basic)

Методы расширения позволяют добавлять методы в существующий класс. После объявления и включения в область действия метода расширения можно вызвать его как метод экземпляра типа, который он расширяет. Дополнительные сведения о написании метода расширения см. [в разделе как написать метод расширения](./how-to-write-an-extension-method.md).

 Следующие инструкции относятся к методу расширения `PrintAndPunctuate` , который отображает экземпляр строки, который вызывает его, за которым следует любое значение, отправляемое для второго параметра `punc` .

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

Метод должен находиться в области видимости при его вызове.

### <a name="to-call-an-extension-method"></a>Вызов метода расширения

1. Объявите переменную с типом данных первого параметра метода расширения. Для необходимо `PrintAndPunctuate` иметь <xref:System.String> переменную:

    ```vb
    Dim example = "Ready"
    ```

2. Эта переменная вызывает метод расширения, и его значение привязывается к первому параметру, `aString` . Отобразится следующая инструкция вызова `Ready?` .

    ```vb
    example.PrintAndPunctuate("?")
    ```

     Обратите внимание, что вызов этого метода расширения выглядит так же, как вызов любого метода <xref:System.String> экземпляра, для которого требуется один параметр:

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. Объявите другую строковую переменную и снова вызовите метод, чтобы увидеть, что он работает с любой строкой.

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     Результат в этом случае: `or not!!!` .

## <a name="example"></a>Пример

 Следующий код является полным примером создания и использования простого метода расширения.

```vb
Imports System.Runtime.CompilerServices
Imports ConsoleApplication1.StringExtensions

Module Module1

    Sub Main()

        Dim example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")

        Dim example2 = "Goodbye"
        example2.PrintAndPunctuate("?")
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module

' Output:
' Hello.
' Hello!!!!
' Goodbye?
```

## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Написание метода расширения](./how-to-write-an-extension-method.md)
- [Методы расширения](./extension-methods.md)
- [Область видимости в Visual Basic](../declared-elements/scope.md)
