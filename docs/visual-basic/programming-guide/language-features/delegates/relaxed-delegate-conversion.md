---
description: 'Дополнительные сведения о: неявное преобразование делегата (Visual Basic)'
title: Неявное преобразование делегата
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: 36917017cd29d2c71f0c04ca9545b7d4e90c644e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428497"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Неявное преобразование делегата (Visual Basic)

Неявное преобразование делегатов позволяет назначать процедуры и функции делегатам или обработчикам, даже если их сигнатуры не идентичны. Таким образом, привязка к делегатам будет соответствовать привязке, уже разрешенной для вызовов методов.  
  
## <a name="parameters-and-return-type"></a>Параметры и возвращаемый тип  

 Вместо точного соответствия сигнатуры для ослабленного преобразования требуется выполнение следующих условий, если параметр `Option Strict` имеет значение `On` .  
  
- Должно существовать расширяющее преобразование из типа данных каждого параметра делегата в тип данных соответствующего параметра назначенной функции или `Sub` . В следующем примере делегат `Del1` имеет один параметр — `Integer` . Параметр `m` в назначенных лямбда-выражениях должен иметь тип данных, для которого существует расширяющее преобразование `Integer` , например `Long` или `Double` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     Сужающие преобразования разрешены, только если `Option Strict` для задано значение `Off` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- Расширяющее преобразование должно существовать в противоположном направлении от возвращаемого типа назначенной функции или `Sub` к типу возвращаемого значения делегата. В следующих примерах текст каждого назначенного лямбда-выражения должен иметь тип данных, который расширяется до, `Integer` так как тип возвращаемого значения `del1` — `Integer` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 Если параметр `Option Strict` имеет значение `Off` , расширяющееся ограничение удаляется в обоих направлениях.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>Пропуск спецификаций параметров  

 Ослабленные делегаты также позволяют полностью опускать спецификации параметров в назначенном методе:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 Обратите внимание, что нельзя указать некоторые параметры и опустить другие.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 Возможность опускать параметры полезна в таких ситуациях, как определение обработчика событий, в котором участвуют несколько сложных параметров. Аргументы некоторых обработчиков событий не используются. Вместо этого обработчик напрямую обращается к состоянию элемента управления, в котором регистрируется событие, и игнорирует аргументы. Ослабленные делегаты позволяют опускать аргументы в таких объявлениях, если результат неоднозначности. В следующем примере полностью указанный метод `OnClick` может быть переписан как `RelaxedOnClick` .  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Примеры AddressOf  

 Лямбда-выражения используются в предыдущих примерах для упрощения просмотра связей типов. Однако для назначений делегатов, которые используют, или, разрешены те же ограничения `AddressOf` `Handles` `AddHandler` .  
  
 В следующем примере функции,, `f1` `f2` `f3` и `f4` могут быть назначены `Del1` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 Следующий пример допустим только в том случае `Option Strict` , если параметр имеет значение `Off` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>Удаление возвращаемых функций  

 Неявное преобразование делегата позволяет присвоить функцию `Sub` делегату, фактически игнорируя возвращаемое значение функции. Однако нельзя присвоить значение `Sub` делегату функции. В следующем примере адрес функции `doubler` назначается `Sub` делегату `Del3` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>См. также

- [Лямбда-выражения](../procedures/lambda-expressions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
- [Делегаты](index.md)
- [Практическое руководство. Передача процедур другой процедуре в Visual Basic](how-to-pass-procedures-to-another-procedure.md)
- [Вывод локального типа](../variables/local-type-inference.md)
- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
