---
title: MustInherit
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 6502da947ae331a26e66d8ce2dbcda46e4172a6e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867955"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)

Указывает, что класс может использоваться только в качестве базового класса и не может создавать объект непосредственно из него.  
  
## <a name="remarks"></a>Remarks  

 Целью *базового класса* (также известного как *абстрактный класс*) является определение функций, общих для всех классов, производных от него. Это позволяет сохранить производные классы от необходимости переопределять общие элементы. В некоторых случаях эта общая функциональность не является достаточно полной для создания пригодного для использования объекта, и каждый производный класс определяет недостающие функциональные возможности. В этом случае необходимо, чтобы код, создающий объекты, был создан только из производных классов. `MustInherit`Для этого используйте в базовом классе.  
  
 Другим применением `MustInherit` класса является ограничение переменной набором связанных классов. Можно определить базовый класс и получить от него все связанные с ним классы. Базовый класс не обязан предоставлять функциональные возможности, общие для всех производных классов, но он может служить фильтром для присвоения значений переменным. Если в используемом коде объявляется переменная в качестве базового класса, Visual Basic позволяет назначить этой переменной только один из производных классов.  
  
 .NET Framework определяет несколько `MustInherit` классов, между ними, <xref:System.Array> <xref:System.Enum> и <xref:System.ValueType> . <xref:System.ValueType> — Это пример базового класса, который ограничивают переменную. Все типы значений являются производными от <xref:System.ValueType> . Если переменная объявляется как <xref:System.ValueType> , то этой переменной можно назначить только типы значений.  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** Можно использовать `MustInherit` только в `Class` операторе.  
  
- **Комбинированные модификаторы.** Нельзя указывать `MustInherit` вместе с `NotInheritable` в одном объявлении.  
  
## <a name="example"></a>Пример  

 В следующем примере показано принудительное наследование и принудительное переопределение. Базовый класс `shape` определяет переменную `acrossLine` . Классы `circle` и `square` являются производными от `shape` . Они наследуют определение `acrossLine` , но они должны определять функцию, `area` так как это вычисление различается для каждого вида фигуры.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 Можно объявлять `shape1` и `shape2` иметь тип `shape` . Однако нельзя создать объект из, `shape` поскольку он не имеет функций функции `area` и помечен как `MustInherit` .  
  
 Поскольку они объявляются как `shape` , переменные `shape1` и `shape2` ограничены объектами из производных классов `circle` и `square` . Visual Basic не позволяет назначать другим объектам эти переменные, что обеспечивает высокий уровень безопасности типов.  
  
## <a name="usage"></a>Использование  

 `MustInherit`Модификатор можно использовать в этом контексте:  
  
 [Оператор Class](../statements/class-statement.md)  
  
## <a name="see-also"></a>См. также

- [Inherits Statement](../statements/inherits-statement.md)
- [NotInheritable](notinheritable.md)
- [Ключевые слова](../keywords/index.md)
- [Основы наследования](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
