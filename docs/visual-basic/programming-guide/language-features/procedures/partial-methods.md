---
title: Разделяемые методы
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: 0e7c1315df50e83c919270f76405e80862bdd03b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071265"
---
# <a name="partial-methods-visual-basic"></a>Разделяемые методы (Visual Basic)

Разделяемые методы позволяют разработчикам вставлять в код пользовательскую логику. Как правило, код является частью класса, созданного конструктором. Разделяемые методы определяются в разделяемом классе, созданном генератором кода, и обычно используются для предоставления уведомлений о том, что что-то изменилось. Они позволяют разработчику указать пользовательское поведение в ответ на изменение.  
  
 Конструктор генератора кода определяет только сигнатуру метода и один или несколько вызовов метода. Разработчики могут предоставлять реализации для метода, если им нужно настроить поведение созданного кода. Если реализация не предоставлена, то вызовы метода удаляются компилятором, что приводит к дополнительной нагрузке на производительность.  
  
## <a name="declaration"></a>Объявление  

 Созданный код помечает определение разделяемого метода, помещая ключевое слово `Partial` в начале строки подписи.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 Определение должно соответствовать следующим условиям:  
  
- Метод должен быть, а `Sub` не `Function` .  
  
- Тело метода должно оставаться пустым.  
  
- Модификатор доступа должен иметь значение `Private` .  
  
## <a name="implementation"></a>Реализация  

 Реализация состоит в основном за заполнением тела разделяемого метода. Реализация обычно находится в отдельном разделяемом классе из определения и написана разработчиком, желающим расширить созданный код.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 В предыдущем примере сигнатура дублируется в объявлении точно, но возможны вариации. В частности, можно добавить другие модификаторы, например `Overloads` или `Overrides` . Допускается только один `Overrides` модификатор. Дополнительные сведения об модификаторах методов см. в разделе [оператор подраздела](../../../language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Использовать  

 Разделяемый метод вызывается так же, как и любая другая `Sub` процедура. Если метод реализован, вычисляются аргументы и выполняется тело метода. Однако помните, что реализация разделяемого метода является необязательной. Если метод не реализован, вызов этого метода не имеет результата, и выражения, передаваемые в качестве аргументов в метод, не оцениваются.  
  
## <a name="example"></a>Пример  

 В файле Product. Designer. vb Определите `Product` класс, имеющий `Quantity` свойство.  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 В файле Product. vb укажите реализацию для `QuantityChanged` .  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 Наконец, в методе Main проекта объявите `Product` экземпляр и укажите начальное значение для его `Quantity` Свойства.  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 Появится окно сообщения, в котором отображается следующее сообщение:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>См. также

- [Оператор Sub](../../../language-reference/statements/sub-statement.md)
- [Подпрограммы](./sub-procedures.md)
- [Необязательные параметры](./optional-parameters.md)
- [Partial](../../../language-reference/modifiers/partial.md)
- [Создание кода в LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Добавление бизнес-логики с использованием разделяемых методов](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
