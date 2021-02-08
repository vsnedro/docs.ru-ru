---
description: 'Дополнительные сведения о инструкции: Exit (Visual Basic)'
title: Оператор Exit
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 54af7fbf908dbad829cf6f08bf442dfe85e35610
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769132"
---
# <a name="exit-statement-visual-basic"></a>Оператор Exit (Visual Basic)

Выходит из процедуры или блока и немедленно передает управление оператору после вызова процедуры или определения блока.

## <a name="syntax"></a>Синтаксис

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>Операторы

 `Exit Do`  
 Немедленно завершает работу `Do` цикла, в котором он отображается. Выполнение продолжится с оператора, следующего за `Loop` оператором. `Exit Do` может использоваться только внутри `Do` цикла. При использовании внутри вложенных `Do` циклов `Exit Do` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.

 `Exit For`  
 Немедленно завершает работу `For` цикла, в котором он отображается. Выполнение продолжится с оператора, следующего за `Next` оператором. `Exit For`может использоваться только внутри `For` цикла... `Next` или `For Each` ... `Next` При использовании внутри вложенных `For` циклов `Exit For` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.

 `Exit Function`  
 Немедленно завершает процедуру, `Function` в которой она отображается. Выполнение продолжится с оператора, следующего за инструкцией, вызвавшей `Function` процедуру. `Exit Function` может использоваться только внутри `Function` процедуры.

 Чтобы указать возвращаемое значение, можно присвоить значение имени функции в строке перед `Exit Function` инструкцией. Чтобы присвоить возвращаемое значение и выйти из функции в одной инструкции, можно использовать [оператор return](return-statement.md).

 `Exit Property`  
 Немедленно завершает процедуру, `Property` в которой она отображается. Выполнение продолжится инструкцией, вызвавшей `Property` процедуру, то есть с инструкцией, запрашивающей или задавая значение свойства. `Exit Property` может использоваться только внутри `Get` процедуры свойства или `Set` .

 Чтобы указать возвращаемое значение в `Get` процедуре, можно присвоить значение имени функции в строке перед `Exit Property` инструкцией. Чтобы присвоить возвращаемое значение и выйти из `Get` процедуры в одной инструкции, можно использовать `Return` инструкцию.

 В `Set` процедуре `Exit Property` инструкция эквивалентна `Return` инструкции.

 `Exit Select`  
 Немедленно завершает работу `Select Case` блока, в котором он отображается. Выполнение продолжится с оператора, следующего за `End Select` оператором. `Exit Select` может использоваться только внутри `Select Case` оператора.

 `Exit Sub`  
 Немедленно завершает процедуру, `Sub` в которой она отображается. Выполнение продолжится с оператора, следующего за инструкцией, вызвавшей `Sub` процедуру. `Exit Sub` может использоваться только внутри `Sub` процедуры.

 В `Sub` процедуре `Exit Sub` инструкция эквивалентна `Return` инструкции.

 `Exit Try`  
 Немедленно завершает работу `Try` блока или, `Catch` в котором он отображается. Выполнение продолжится с `Finally` блока, если таковой имеется, или с оператором, который следует `End Try` в противном случае. `Exit Try` может использоваться только внутри `Try` `Catch` блока или, а не внутри `Finally` блока.

 `Exit While`  
 Немедленно завершает работу `While` цикла, в котором он отображается. Выполнение продолжится с оператора, следующего за `End While` оператором. `Exit While` может использоваться только внутри `While` цикла. При использовании внутри вложенных `While` циклов `Exit While` передает управление циклу, который является одним вложенным уровнем над циклом, где `Exit While` происходит.

## <a name="remarks"></a>Remarks

Не путайте `Exit` Операторы с `End` операторами. `Exit` не определяет конец инструкции.

## <a name="example"></a>Пример

В следующем примере условие цикла останавливает цикл, если `index` переменная больше 100. `If`Однако инструкция в цикле приводит к `Exit Do` остановке цикла, если переменная индекса больше 10.

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>Пример

В следующем примере возвращаемое значение присваивается имени функции `myFunction` , а затем используется `Exit Function` для возврата из функции:

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a>Пример

В следующем примере [оператор return](return-statement.md) используется для назначения возвращаемого значения и выхода из функции:

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a>См. также

- [Оператор Continue](continue-statement.md)
- [Оператор Do…Loop](do-loop-statement.md)
- [End, инструкция](end-statement.md)
- [Оператор For Each…Next](for-each-next-statement.md)
- [Оператор For…Next](for-next-statement.md)
- [Оператор Function](function-statement.md)
- [Оператор Return](return-statement.md)
- [Оператор Stop](stop-statement.md)
- [Оператор Sub](sub-statement.md)
- [Оператор Try...Catch...Finally](try-catch-finally-statement.md)
