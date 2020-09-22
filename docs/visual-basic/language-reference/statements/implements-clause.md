---
title: Предложение Implements
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 7c95cf76b1bac24e2a0f20857b8984d54ebbea85
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866166"
---
# <a name="implements-clause-visual-basic"></a>Предложение Implements (Visual Basic)

Указывает, что член класса или структуры предоставляет реализацию для члена, определенного в интерфейсе.  
  
## <a name="remarks"></a>Remarks  

`Implements`Ключевое слово не совпадает с [оператором Implements](implements-statement.md). `Implements`Инструкция используется для указания того, что класс или структура реализует один или несколько интерфейсов, а затем для каждого элемента используется `Implements` ключевое слово для указания интерфейса и члена, который он реализует.

Если класс или структура реализует интерфейс, он должен включать `Implements` инструкцию сразу после оператора [Class](class-statement.md) или [Structure](structure-statement.md), и она должна реализовывать все члены, определенные интерфейсом.

## <a name="reimplementation"></a>Воссоздании  

В производном классе можно повторно реализовать член интерфейса, который уже реализован в базовом классе. Это отличается от переопределения члена базового класса в следующих отношениях.

- Член базового класса не обязательно должен быть [переопределяемым](../modifiers/overridable.md) для повторной реализации.
- Элемент можно повторно реализовать с другим именем.

`Implements`Ключевое слово можно использовать в следующих контекстах:

- [Оператор Event](event-statement.md)
- [Оператор Function](function-statement.md)
- [Property Statement](property-statement.md)
- [Оператор Sub](sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Оператор Implements](implements-statement.md)
- [Оператор Interface](interface-statement.md)
- [Оператор Class](class-statement.md)
- [Оператор Structure](structure-statement.md)
