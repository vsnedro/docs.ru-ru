---
title: Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: e7975dc767ae652359c904271d6610be34e4cb80
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870241"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам

Использование переменной итерации в лямбда-выражении может привести к непредвиденным результатам. Вместо этого создайте локальную переменную в цикле и присвойте ей значение переменной итерации.  
  
 Это предупреждение появляется при использовании переменной итерации цикла в лямбда-выражении, объявленном внутри цикла. Например, следующий пример приводит к отображению предупреждения.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 В следующем примере показаны непредвиденные результаты, которые могут возникнуть.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 `For`Цикл создает массив лямбда-выражений, каждый из которых возвращает значение переменной итерации цикла `i` . При вычислении лямбда-выражений в `For Each` цикле можно ожидать отображения значений 0, 1, 2, 3 и 4, последовательные значения `i` в `For` цикле. Вместо этого отображается последнее значение, `i` Отображаемое пять раз:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42324  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Присвойте значение переменной итерации локальной переменной и используйте локальную переменную в лямбда-выражении.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>См. также

- [Лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md)
