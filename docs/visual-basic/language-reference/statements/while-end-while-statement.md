---
description: 'Дополнительные сведения: while... Оператор End While (Visual Basic)'
title: Оператор While…End While
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: ab452e2d9446c9c44b952c6ebf026f7a6f9080cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787582"
---
# <a name="whileend-while-statement-visual-basic"></a>Оператор While... End While (Visual Basic)

Выполняет последовательность операторов, если заданное условие имеет значение `True` .  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`condition`|Обязательный. Выражение `Boolean`. Если `condition` имеет значение `Nothing` , Visual Basic обрабатывает его как `False` .|  
|`statements`|Необязательный элемент. Один или несколько следующих инструкций `While` , которые выполняются каждый раз, `condition` — `True` .|  
|`Continue While`|Необязательный элемент. Передает управление следующей итерации `While` блока.|  
|`Exit While`|Необязательный элемент. Передает управление за пределы `While` блока.|  
|`End While`|Обязательный элемент. Завершает определение блока `While`.|  
  
## <a name="remarks"></a>Remarks  

 Используйте `While...End While` структуру, если необходимо повторить набор инструкций неопределенное количество раз, если условие остается `True` . Если вы хотите обеспечить большую гибкость при тестировании условия или результата тестирования, вы можете предпочесть оператору [Do... Loop, инструкция](do-loop-statement.md). Если нужно повторить инструкции заданное число раз, то [для... ](for-next-statement.md) Обычно лучше подходит следующий оператор.  
  
> [!NOTE]
> `While`Ключевое слово также используется в [инструкции Do... Оператор Loop](do-loop-statement.md), [предложение Skip While](../queries/skip-while-clause.md) и [предложение Take While](../queries/take-while-clause.md).  
  
 Если `condition` имеет значение `True` , все `statements` выполняется до тех пор, пока `End While` не будет обнаружен оператор. Затем элемент управления возвращается в `While` инструкцию и `condition` снова проверяется. Если `condition` по-прежнему `True` , процесс повторяется. Если это так `False` , управление передается оператору, следующему за `End While` оператором.  
  
 `While`Оператор всегда проверяет условие перед началом цикла. Цикл продолжается, пока условие остается `True` . Если параметр `condition` имеет значение `False` при первом входе в цикл, он не выполняется даже один раз.  
  
 `condition`Обычно результат сравнения двух значений, но может быть любым выражением, результатом вычисления которого является [логическое значение типа данных](../data-types/boolean-data-type.md) ( `True` или `False` ). Это выражение может включать в себя значение другого типа данных, например числовой тип, который был преобразован в `Boolean` .  
  
 Можно вложить `While` циклы, поместив один цикл в другой. Можно также вкладывать различные виды управляющих структур друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Выйти, пока  

 Оператор [Exit While](exit-statement.md) может предоставить другой способ выхода из `While` цикла. `Exit While` немедленно передает управление оператору, который следует за `End While` оператором.  
  
 Обычно используется `Exit While` после вычисления некоторого условия (например, в `If...Then...Else` структуре). Может потребоваться выйти из цикла, если обнаруживается условие, которое делает ненужным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Можно использовать `Exit While` при проверке условия, которое может вызвать *бесконечный цикл*, что является циклом, который может выполнять очень большое или даже бесконечное число раз. Затем можно использовать `Exit While` для экранирования цикла.  
  
 Любое количество операторов можно разместить `Exit While` в любом месте `While` цикла.  
  
 При использовании внутри вложенных `While` циклов `Exit While` передает управление за пределы самого внутреннего цикла и в следующий более высокий уровень вложенности.  
  
 `Continue While`Оператор немедленно передает управление следующей итерации цикла. Дополнительные сведения см. в разделе [оператор continue](continue-statement.md).  
  
## <a name="example"></a>Пример  

 В следующем примере операторы в цикле продолжают выполняться до тех пор, пока `index` переменная не будет больше 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Пример  

 В следующем примере показано использование `Continue While` `Exit While` операторов и.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Пример  

 В следующем примере считываются все строки в текстовом файле. <xref:System.IO.File.OpenText%2A>Метод открывает файл и возвращает объект <xref:System.IO.StreamReader> , считывающий символы. В `While` условии <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, содержит ли файл дополнительные символы.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>См. также

- [Циклические структуры](../../programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор Do…Loop](do-loop-statement.md)
- [Оператор For…Next](for-next-statement.md)
- [Логический тип данных](../data-types/boolean-data-type.md)
- [Вложенные структуры управления](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](exit-statement.md)
- [Оператор Continue](continue-statement.md)
