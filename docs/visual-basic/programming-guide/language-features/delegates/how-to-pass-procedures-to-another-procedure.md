---
title: Практическое руководство. Передача процедур другой процедуре
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 36f623068372614ae034a8a7b31bffb7496f98b1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410699"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Практическое руководство. Передача процедур другой процедуре в Visual Basic
В этом примере показано, как использовать делегаты для передачи процедуры в другую процедуру.  
  
 Делегат — это тип, который можно использовать как любой другой тип в Visual Basic. `AddressOf`Оператор возвращает объект делегата при применении к имени процедуры.  
  
 Этот пример содержит процедуру с параметром делегата, который может принимать ссылку на другую процедуру, полученную с помощью `AddressOf` оператора.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Создание делегата и процедур сопоставления  
  
1. Создайте делегат с именем `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, совпадающими с `MathOperator` , чтобы сигнатуры совпадали.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Создайте процедуру с именем `SubtractNumbers` и соответствующей сигнатурой `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Создайте процедуру с именем `DelegateTest` , которая принимает делегат в качестве параметра.  
  
     Эта процедура может принять ссылку на `AddNumbers` или `SubtractNumbers` , поскольку их сигнатуры соответствуют `MathOperator` сигнатуре.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Создайте процедуру с именем `Test` , которая вызывает `DelegateTest` один раз с делегатом для в `AddNumbers` качестве параметра и снова с делегатом для в `SubtractNumbers` качестве параметра.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     При `Test` вызове метода сначала отображается результат действия `AddNumbers` с `5` и `3` , который равен 8. Затем отображается результат работы функции `SubtractNumbers` `9` и `3` , что равно 6.  
  
## <a name="see-also"></a>См. также раздел

- [Делегаты](index.md)
- [Оператор AddressOf](../../../language-reference/operators/addressof-operator.md)
- [Оператор Delegate](../../../language-reference/statements/delegate-statement.md)
- [Практическое руководство. Вызов метода делегата](how-to-invoke-a-delegate-method.md)
