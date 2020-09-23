---
title: Специальные символы в коде
ms.date: 07/20/2015
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
ms.openlocfilehash: 60f815f0d30fa785f4a2166db5a041d3851aa954
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097830"
---
# <a name="special-characters-in-code-visual-basic"></a>Специальные символы в коде (Visual Basic)

Иногда в коде необходимо использовать специальные символы, то есть символы, не являющиеся алфавитными или числовыми. Знаки пунктуации и специальные символы в Visual Basic кодировке имеют различные варианты использования, от организации текста программы до определения задач, выполняемых компилятором или скомпилированной программой. Эти знаки не определяют операции, подлежащие выполнению.  
  
## <a name="parentheses"></a>Круглые скобки  

 Используйте круглые скобки при определении процедуры, например `Sub` или `Function` . Все списки аргументов процедур необходимо заключать в круглые скобки. Также круглые скобки используются для помещения переменных или аргументов в логические группы, особенно для переопределения порядка приоритета операторов по умолчанию в сложном выражении. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 После выполнения предыдущего кода значение `d` равно 8,225, а значение `e` равно 3. Вычисление для `d` использует приоритет по умолчанию `/` over `+` и эквивалентен `d = b + (c / a)` . Круглые скобки в вычислении для `e` переопределения приоритета по умолчанию.  
  
## <a name="separators"></a>Разделители  

 Разделители выполняют свои имена: они разделяют разделы кода. В Visual Basic символ разделителя является двоеточием ( `:` ). Используйте разделители, если требуется включить несколько операторов в одну строку, а не отдельные строки. Это экономит пространство и повышает удобочитаемость кода. В следующем примере показаны три инструкции, разделенные двоеточиями.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Дополнительные сведения см. [в разделе инструкции. разбиение и объединение инструкций в коде](how-to-break-and-combine-statements-in-code.md).  
  
 Символ двоеточия ( `:` ) также используется для обозначения метки оператора. Дополнительные сведения см. [в разделе инструкции. Метки](how-to-label-statements.md).  
  
## <a name="concatenation"></a>Объединение  

 Используйте `&` оператор для *объединения*или связывания строк. Не путайте его с `+` оператором, который добавляет вместе числовые значения. При использовании `+` оператора для сцепления с числовыми значениями можно получить неверные результаты. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 После выполнения предыдущего кода значение `resultA` равно 21,01, а значение `resultB` равно "10,0111".  
  
## <a name="member-access-operators"></a>Операторы доступа к членам  

 Для доступа к члену типа используется оператор dot ( `.` ) или восклицательный знак ( `!` ) между именем типа и именем члена.  
  
### <a name="dot--operator"></a>Точка (.) Станции  

 Используйте `.` оператор для класса, структуры, интерфейса или перечисления в качестве оператора доступа к членам. Элемент может быть полем, свойством, событием или методом. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Восклицательный знак (!) Станции  

 Оператор используется `!` только для класса или интерфейса в качестве оператора доступа в словаре. Класс или интерфейс должен иметь свойство по умолчанию, принимающее один `String` аргумент. Идентификатор, непосредственно следующий за `!` оператором, становится значением аргумента, передаваемым в свойство по умолчанию в виде строки. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 В трех строках вывода `MsgBox` отображается значение `32856` . В первой строке используется традиционный доступ к свойству `index` , а во втором используется тот факт, который `index` является свойством по умолчанию класса `hasDefault` , а третий использует словарный доступ к классу.  
  
 Обратите внимание, что второй операнд `!` оператора должен быть допустимым Visual Basic идентификатором, не заключенным в двойные кавычки ( `" "` ). Иными словами, нельзя использовать строковый литерал или строковую переменную. Следующее изменение в последней строке `MsgBox` вызова приводит к ошибке, поскольку `"X"` является заключенным строковым литералом.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> Ссылки на коллекции по умолчанию должны быть явными. В частности, нельзя использовать `!` оператор для переменной с поздним связыванием.  
  
 `!`Символ также используется в качестве `Single` символа типа.  
  
## <a name="see-also"></a>См. также

- [Соглашения о структуре программы и коде](program-structure-and-code-conventions.md)
- [Символы типов](../language-features/data-types/type-characters.md)
