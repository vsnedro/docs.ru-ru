---
description: 'Дополнительные сведения: определение типа объекта (Visual Basic)'
title: Определение типа объекта
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 0cf64b6dde74b98edaf055537533cb648ed3381a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434411"
---
# <a name="determining-object-type-visual-basic"></a>Определение типа объекта (Visual Basic)

Универсальные объектные переменные (то есть переменные, объявляемые как `Object` ) могут содержать объекты из любого класса. При использовании переменных типа `Object` может потребоваться выполнить различные действия на основе класса объекта. Например, некоторые объекты могут не поддерживать конкретное свойство или метод. Visual Basic предоставляет два способа определения типа объекта, хранящегося в объектной переменной: `TypeName` функции и `TypeOf...Is` оператора.  
  
## <a name="typename-and-typeofis"></a>TypeName и TypeOf... Рекомендуется  

 `TypeName`Функция возвращает строку и является лучшим выбором, если необходимо сохранить или отобразить имя класса объекта, как показано в следующем фрагменте кода:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 `TypeOf...Is`Оператор является лучшим выбором для тестирования типа объекта, так как он гораздо быстрее, чем эквивалентное сравнение строк с помощью `TypeName` . В следующем фрагменте кода используется `TypeOf...Is` `If...Then...Else` оператор:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 В этом случае следует соблюдать осторожность. `TypeOf...Is`Оператор возвращает значение `True` , если объект относится к определенному типу или является производным от определенного типа. Почти все, что выполняется с Visual Basic, включает объекты, которые включают в себя некоторые элементы, которые обычно не считаются объектами, например строками и целыми числами. Эти объекты являются производными от методов и наследуют от них <xref:System.Object> . Если передается `Integer` и вычисляется с помощью `Object` , `TypeOf...Is` оператор возвращает `True` . В следующем примере сообщается, что параметр `InParam` является `Object` и, и `Integer` :  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 В следующем примере используются методы `TypeOf...Is` и `TypeName` для определения типа объекта, переданного в него в `Ctrl` аргументе. `TestObject`Процедура вызывается `ShowType` с тремя различными видами элементов управления.  
  
#### <a name="to-run-the-example"></a>Запуск примера  
  
1. Создайте новый проект приложения Windows и добавьте в <xref:System.Windows.Forms.Button> форму элемент управления, <xref:System.Windows.Forms.CheckBox> элемент управления и <xref:System.Windows.Forms.RadioButton> элемент управления.  
  
2. В форме нажмите кнопку, чтобы вызвать `TestObject` процедуру.  
  
3. Добавьте в форму следующий код:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Вызов свойства или метода с помощью строкового имени](calling-a-property-or-method-using-a-string-name.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Оператор If…Then…Else](../../../language-reference/statements/if-then-else-statement.md)
- [Тип данных String](../../../language-reference/data-types/string-data-type.md)
- [Тип данных Integer](../../../language-reference/data-types/integer-data-type.md)
