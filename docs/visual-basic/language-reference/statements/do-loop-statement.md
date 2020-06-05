---
title: Оператор Do…Loop
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: a9ec6caccbe161a39b592a642a938b81bae911a6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404788"
---
# <a name="doloop-statement-visual-basic"></a>Оператор Do...Loop (Visual Basic)
Повторяет блок инструкций `Boolean` , пока условие находится `True` в состоянии или до тех пор, пока условие не станет `True` .  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`Do`|Обязательный. Запускает определение `Do` цикла.|  
|`While`|Является обязательным, если используется параметр `Until`. Повторите цикл, пока `condition` не будет `False` .|  
|`Until`|Является обязательным, если используется параметр `While`. Повторите цикл, пока `condition` не будет `True` .|  
|`condition`|Необязательный элемент. Выражение `Boolean`. Если `condition` имеет значение `Nothing` , Visual Basic обрабатывает его как `False` .|  
|`statements`|Необязательный элемент. Одна или несколько инструкций, повторяемых в, или до, `condition` имеют `True` .|  
|`Continue Do`|Необязательный элемент. Передает управление следующей итерации `Do` цикла.|  
|`Exit Do`|Необязательный элемент. Передает управление за пределы `Do` цикла.|  
|`Loop`|Обязательный. Завершает определение `Do` цикла.|  
  
## <a name="remarks"></a>Комментарии  
 Используйте `Do...Loop` структуру, если нужно повторить набор инструкций неопределенное число раз, пока не будет удовлетворено условие. Если нужно повторить инструкции заданное число раз, то [для... ](for-next-statement.md)Обычно лучше подходит следующий оператор.  
  
 Можно использовать либо `While` , либо `Until` , чтобы указать `condition` , но не оба.  
  
 Тест можно выполнять `condition` только один раз, в начале или в конце цикла. Если проверка выполняется в `condition` начале цикла (в `Do` операторе), цикл может не выполняться даже один раз. Если протестировать в конце цикла (в `Loop` операторе), цикл всегда выполняется по крайней мере один раз.  
  
 Условие обычно является результатом сравнения двух значений, но может быть любым выражением, результатом вычисления которого является [логическое значение типа данных](../data-types/boolean-data-type.md) ( `True` или `False` ). Сюда относятся значения других типов данных, например числовые типы, которые были преобразованы в `Boolean` .  
  
 Можно вложить `Do` циклы, поместив один цикл в другой. Можно также вкладывать различные виды управляющих структур друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
> Эта `Do...Loop` структура обеспечивает большую гибкость, чем [while... Оператор End While](while-end-while-statement.md) , так как он позволяет решить, следует ли завершать цикл при `condition` остановке `True` или при первом преобразовании `True` . Он также позволяет тестироваться `condition` как в начале, так и в конце цикла.  
  
## <a name="exit-do"></a>Выйти  
 Оператор [Exit Do](exit-statement.md) может предоставить альтернативный способ выхода из `Do…Loop` . `Exit Do`немедленно передает управление оператору, следующему за `Loop` оператором.  
  
 `Exit Do`часто используется после вычисления некоторого условия, например в `If...Then...Else` структуре. Может потребоваться выйти из цикла, если обнаруживается условие, которое делает ненужным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Одно из них `Exit Do` — Проверка на наличие условия, которое может вызвать *бесконечный цикл*, то есть цикл, который может выполнять большое или даже бесконечное число раз. `Exit Do`Для экранирования цикла можно использовать.  
  
 В можно включить любое количество `Exit Do` операторов в любом месте `Do…Loop` .  
  
 При использовании внутри вложенных `Do` циклов `Exit Do` передает управление за пределы самого внутреннего цикла и в следующий более высокий уровень вложенности.  
  
## <a name="example"></a>Пример  
 В следующем примере операторы в цикле продолжают выполняться до тех пор, пока `index` переменная не будет больше 10. `Until`Предложение находится в конце цикла.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Пример  
 В следующем примере `While` вместо предложения используется предложение, которое `Until` `condition` проверяется в начале цикла, а не в конце.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Пример  
 В следующем примере `condition` останавливается цикл, если `index` переменная больше 100. `If`Однако инструкция в цикле приводит к `Exit Do` остановке цикла, если переменная индекса больше 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Пример  
 В следующем примере считываются все строки в текстовом файле. <xref:System.IO.File.OpenText%2A>Метод открывает файл и возвращает объект <xref:System.IO.StreamReader> , считывающий символы. В `Do...Loop` условии <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет наличие дополнительных символов.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>См. также раздел

- [Циклические структуры](../../programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор For…Next](for-next-statement.md)
- [Логический тип данных](../data-types/boolean-data-type.md)
- [Вложенные структуры управления](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](exit-statement.md)
- [Оператор While…End While](while-end-while-statement.md)
