---
description: Дополнительные сведения см. в статье как создать лямбда-выражение (Visual Basic)
title: Практическое руководство. Создание лямбда-выражения
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 386d40c1e2021c9b02b2f785300c4e978b4da87d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472570"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Практическое руководство. Создание лямбда-выражения (Visual Basic)

*Лямбда-выражение* — это функция или подпрограммы, у которой нет имени. Лямбда-выражение может использоваться везде, где допустим тип делегата.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Создание однострочной функции лямбда-выражения  
  
1. В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Function` , как показано в следующем примере:  
  
     `Dim add1 =`   `Function`  
  
2. В скобках сразу после `Function` введите параметры функции. Обратите внимание, что имя не указывается после `Function` .  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. После списка параметров введите одно выражение в качестве текста функции. Значение, которое вычисляется выражением, — это значение, возвращаемое функцией. Не используйте `As` предложение, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     Лямбда-выражение вызывается путем передачи целочисленного аргумента.  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. Кроме того, тот же результат достигается в следующем примере:  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Создание однострочной подпрограммы лямбда-выражения  
  
1. В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Sub` , как показано в следующем примере.  
  
     `Dim add1 =`   `Sub`  
  
2. В скобках сразу после `Sub` введите параметры подпрограммы. Обратите внимание, что имя не указывается после `Sub` .  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. После списка параметров введите один оператор в качестве текста подпрограммы.  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     Лямбда-выражение вызывается путем передачи строкового аргумента.  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Создание многострочной функции лямбда-выражения  
  
1. В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Function` , как показано в следующем примере.  
  
     `Dim add1 =`   `Function`  
  
2. В скобках сразу после `Function` введите параметры функции. Обратите внимание, что имя не указывается после `Function` .  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. Нажмите клавишу ВВОД. `End Function`Инструкция автоматически добавляется.  
  
4. В теле функции добавьте следующий код, чтобы создать выражение и вернуть значение. Не используйте `As` предложение, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     Лямбда-выражение вызывается путем передачи целочисленного аргумента.  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Создание многострочной подпрограммы лямбда-выражений  
  
1. В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Sub` , как показано в следующем примере:  
  
     `Dim add1 =`   `Sub`  
  
2. В скобках сразу после `Sub` введите параметры подпрограммы. Обратите внимание, что имя не указывается после `Sub` .  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. Нажмите клавишу ВВОД. `End Sub`Инструкция автоматически добавляется.  
  
4. В теле функции добавьте следующий код для выполнения при вызове подпрограммы.  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     Лямбда-выражение вызывается путем передачи строкового аргумента.  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>Пример  

 Обычно лямбда-выражения используются для определения функции, которую можно передать в качестве аргумента для параметра, тип которого имеет значение `Delegate` . В следующем примере <xref:System.Diagnostics.Process.GetProcesses%2A> метод возвращает массив процессов, запущенных на локальном компьютере. Для <xref:System.Linq.Enumerable.Where%2A> метода из <xref:System.Linq.Enumerable> класса требуется делегат в `Boolean` качестве аргумента. Лямбда-выражение в примере используется для этой цели. Он возвращает `True` для каждого процесса, который имеет только один поток, и выбранные в `filteredList` .  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 Предыдущий пример эквивалентен следующему коду, написанному в синтаксисе Language-Integrated query (LINQ):  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq.Enumerable>
- [Лямбда-выражения](./lambda-expressions.md)
- [Оператор Function](../../../language-reference/statements/function-statement.md)
- [Оператор Sub](../../../language-reference/statements/sub-statement.md)
- [Делегаты](../delegates/index.md)
- [Практическое руководство. Передача процедур другой процедуре в Visual Basic](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [Оператор Delegate](../../../language-reference/statements/delegate-statement.md)
- [Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
