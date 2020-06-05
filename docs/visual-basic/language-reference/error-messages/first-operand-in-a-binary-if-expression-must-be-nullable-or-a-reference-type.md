---
title: Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: ca16c6604ee071668a5c65d7e9052b233e2313c7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403022"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
`If`Выражение может принимать либо два, либо три аргумента. При отправке только двух аргументов первый аргумент должен быть ссылочным типом или типом значения, допускающим значение null. Если первый аргумент принимает значение, отличное от, то `Nothing` возвращается. Если первый аргумент имеет значение `Nothing` , то вычисляется и возвращается второй аргумент.  
  
 Например, следующий код содержит два `If` выражения: один с тремя аргументами и один с двумя аргументами. Выражения вычисляют и возвращают одно и то же значение.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Эта ошибка возникает в следующих выражениях:  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Идентификатор ошибки:** BC33107  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Если не удается изменить код, чтобы первый аргумент являлся типом значения, допускающим значение null, или ссылочным типом, попробуйте преобразовать в выражение с тремя аргументами `If` или в `If...Then...Else` оператор.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>См. также раздел

- [Оператор If](../operators/if-operator.md)
- [Оператор If…Then…Else](../statements/if-then-else-statement.md)
- [Типы значений, допускающие значение null](../../programming-guide/language-features/data-types/nullable-value-types.md)
