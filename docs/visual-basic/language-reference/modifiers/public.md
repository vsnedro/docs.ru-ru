---
title: Общие
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: f2b6a126435b111ef56ee2a9870ea6fbddf87901
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867682"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)

Указывает, что один или несколько объявленных программных элементов не имеют ограничений доступа.  
  
## <a name="remarks"></a>Remarks  

 При публикации компонента или набора компонентов, таких как библиотека классов, обычно требуется, чтобы элементы программирования были доступны любому коду, взаимодействующему со сборкой. Чтобы обеспечить такой неограниченный доступ к элементу, его можно объявить с помощью `Public` .  
  
 Открытый доступ является обычным уровнем для программного элемента, если нет необходимости ограничивать доступ к нему. Обратите внимание, что уровень доступа элемента, объявленного в интерфейсе, модуле, классе или структуре, по умолчанию имеет значение `Public` , если вы не объявили его в противном случае.  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** Можно использовать `Public` только на уровне модуля, интерфейса или пространства имен. Это означает, что контекст объявления для `Public` элемента должен быть исходным файлом, пространством имен, интерфейсом, модулем, классом или структурой и не может быть процедурой.  
  
## <a name="behavior"></a>Поведение  
  
- **Уровень доступа.** Весь код, который может получить доступ к модулю, классу или структуре, может получить доступ к его `Public` элементам.  
  
- **Доступ по умолчанию.** Локальные переменные в процедуре по умолчанию имеют открытый доступ, и в них нельзя использовать какие-либо модификаторы доступа.  
  
- **Модификаторы доступа.** Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*. Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 Модификатор `Public` можно использовать в следующих контекстах:  
  
 [Оператор Class](../statements/class-statement.md)  
  
 [Оператор Const](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Оператор Delegate](../statements/delegate-statement.md)  
  
 [Оператор Dim](../statements/dim-statement.md)  
  
 [Оператор Enum](../statements/enum-statement.md)  
  
 [Оператор Event](../statements/event-statement.md)  
  
 [Оператор Function](../statements/function-statement.md)  
  
 [Оператор Interface](../statements/interface-statement.md)  
  
 [Оператор Module](../statements/module-statement.md)  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Оператор Structure](../statements/structure-statement.md)  
  
 [Оператор Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [От](protected.md)
- [Friend](friend.md)
- [Частная](private.md)
- [Частный защищенный](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
