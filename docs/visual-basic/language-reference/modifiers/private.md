---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 59f1c1666ce38923a2861244fb377007cd0fa992
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874981"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)

Указывает, что один или несколько объявленных программных элементов доступны только в контексте объявления, включая из любых содержащихся в них типов.  
  
## <a name="remarks"></a>Remarks  

 Если программный элемент представляет собственные функции или содержит конфиденциальные данные, обычно требуется ограничить доступ к нему как можно более строгим. Максимальное ограничение достигается за счет предоставления только модулю, классу или структуре, определяющей его доступ. Чтобы ограничить доступ к элементу таким образом, его можно объявить с помощью `Private` .  

> [!NOTE]
> Можно также использовать модификатор [закрытого](private-protected.md) доступа, который делает член доступным из этого класса и из производных классов, расположенных в содержащей его сборке.

## <a name="rules"></a>Правила  

- **Контекст объявления.** `Private` можно использовать только на уровне модуля. Это означает, что контекст объявления для `Private` элемента должен быть модулем, классом или структурой и не может быть исходным файлом, пространством имен, интерфейсом или процедурой.  
  
## <a name="behavior"></a>Поведение  
  
- **Уровень доступа.** Весь код в контексте объявления может обращаться к его `Private` элементам. Сюда входит код внутри содержащегося типа, например вложенный класс или выражение присваивания в перечислении. Ни один код за пределами контекста объявления не может получить доступ к его `Private` элементам.  
  
- **Модификаторы доступа.** Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*. Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 Модификатор `Private` можно использовать в следующих контекстах:  
  
 [Оператор Class](../statements/class-statement.md)  
  
 [Оператор Const](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Оператор Delegate](../statements/delegate-statement.md)  
  
 [Оператор Dim](../statements/dim-statement.md)  
  
 [Оператор Enum](../statements/enum-statement.md)  
  
 [Оператор Event](../statements/event-statement.md)  
  
 [Оператор Function](../statements/function-statement.md)  
  
 [Оператор Interface](../statements/interface-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Оператор Structure](../statements/structure-statement.md)  
  
 [Оператор Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Открытый](public.md)
- [От](protected.md)
- [Friend](friend.md)
- [Частный защищенный](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
