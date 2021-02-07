---
description: 'Дополнительные сведения: SELECT... Оператор Case (Visual Basic)'
title: Оператор Select…Case
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: 4f8edecd0a0b1afd59e182a372e308c3829a9b93
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741137"
---
# <a name="selectcase-statement-visual-basic"></a>Оператор Select...Case (Visual Basic)

Выполняет одну из нескольких групп инструкций в зависимости от значения выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`testexpression`|Обязательный. Выражение. Необходимо вычислить до одного из простейших типов данных (,,,,,,,,,,,,,, `Boolean` `Byte` `Char` `Date` `Double` `Decimal` `Integer` `Long` `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` и `UShort` ).|  
|`expressionlist`|Требуется в `Case` операторе. Список предложений выражений, представляющих значения соответствия для `testexpression` . Несколько предложений выражений разделяются запятыми. Каждое предложение может принимать одну из следующих форм:<br /><br /> -   *expression1* `To` *выражение2*<br />-[ `Is` ] *компарисоноператор* *выражение*<br />-   *выражение*<br /><br /> Используйте `To` ключевое слово, чтобы указать границы диапазона значений соответствия для `testexpression` . Значение `expression1` должно быть меньше или равно значению `expression2` .<br /><br /> Используйте `Is` ключевое слово с оператором сравнения ( `=` , `<>` ,,, `<` `<=` `>` или `>=` ), чтобы указать ограничение на значения сопоставления для `testexpression` . Если `Is` ключевое слово не указано, оно автоматически вставляется перед *компарисоноператор*.<br /><br /> Форма, указывающая только `expression` , рассматривается как особый случай формы, `Is` где *компарисоноператор* — знак равенства ( `=` ). Эта форма вычисляется как `testexpression`  =  `expression` .<br /><br /> Выражения в `expressionlist` могут быть любого типа данных при условии, что они неявно преобразуются в тип, `testexpression` а подходящее значение `comparisonoperator` допустимо для двух типов, с которыми он используется.|  
|`statements`|Необязательный элемент. Одна или несколько следующих инструкций `Case` , которые выполняются, если `testexpression` совпадают с любым предложением в `expressionlist` .|  
|`elsestatements`|Необязательный элемент. Одна или несколько следующих инструкций `Case Else` , которые выполняются, если не `testexpression` соответствуют ни одному из предложений в `expressionlist` ни одной из `Case` инструкций.|  
|`End Select`|Завершает определение `Select` конструкции.... `Case`|  
  
## <a name="remarks"></a>Remarks  

 Если `testexpression` соответствует любому `Case` `expressionlist` предложению, инструкции, следующие за этим `Case` оператором, выполняются до следующей `Case` `Case Else` инструкции, или `End Select` . Затем управление передается следующему оператору `End Select` . Если `testexpression` соответствует `expressionlist` предложению в более чем одном `Case` предложении, выполняются только инструкции, следующие за первым совпадением.  
  
 `Case Else`Оператор используется для представления `elsestatements` для запуска, если между `testexpression` `expressionlist` предложением и в других инструкциях не найдено совпадений `Case` . Хотя это и не является обязательным, рекомендуется иметь `Case Else` в конструкции оператор, `Select Case` обрабатывающий непредвиденные `testexpression` значения. Если `Case` `expressionlist` предложение не совпадает `testexpression` и отсутствует `Case Else` оператор, управление передается оператору ниже `End Select` .  
  
 В каждом предложении можно использовать несколько выражений или диапазонов `Case` . Например, следующая строка допустима.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> `Is`Ключевое слово, используемое в `Case` `Case Else` операторах и, не совпадает с [оператором is](../operators/is-operator.md), который используется для сравнения ссылок на объекты.  
  
 Можно указать диапазоны и несколько выражений для символьных строк. В следующем примере `Case` соответствует любой строке, которая равна «яблоки», имеет значение между «гайкями» и «полный курс» в алфавитном порядке или содержит точно то же значение, что и текущее значение `testItem` .  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Параметр `Option Compare` может влиять на сравнения строк. В `Option Compare Text` строках «яблоки» и «яблоки» сравниваются как одинаковые, но в противном случае — `Option Compare Binary` нет.  
  
> [!NOTE]
> `Case`Оператор с несколькими предложениями может демонстрировать поведение, называемое *сокращенным вычислением*. Visual Basic вычисляет предложения слева направо, и если одно из них создает совпадение с `testexpression` , оставшиеся предложения не оцениваются. Сокращенное вычисление может повысить производительность, но может привести к непредвиденным результатам, если ожидается вычисление каждого выражения в `expressionlist` . Дополнительные сведения об сокращенном вычислении см. в разделе [логические выражения](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Если код в `Case` `Case Else` блоке инструкций или не требует выполнения каких-либо инструкций в блоке, он может выйти из блока с помощью `Exit Select` инструкции. Это немедленно передает управление оператору, приведенному ниже `End Select` .  
  
 `Select Case` конструкции могут быть вложенными. Каждая вложенная `Select Case` конструкция должна иметь соответствующий `End Select` оператор и должна быть полностью заключена в один `Case` `Case Else` блок инструкций или внешней конструкции, `Select Case` внутри которой он вложен.  
  
## <a name="example"></a>Пример  

 В следующем примере конструкция используется `Select Case` для записи строки, соответствующей значению переменной `number` . Вторая `Case` инструкция содержит значение, совпадающее с текущим значением `number` , поэтому инструкция, записывающая "между 6 и 8 включительно", выполняется.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End, инструкция](end-statement.md)
- [Оператор If…Then…Else](if-then-else-statement.md)
- [Оператор Option Compare](option-compare-statement.md)
- [Оператор Exit](exit-statement.md)
