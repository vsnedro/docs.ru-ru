---
description: 'Дополнительные сведения о: Friend (Visual Basic)'
title: Friend
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: ef2444555c05d6a4b24048316e282d269d4b7f1b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774594"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)

Указывает, что один или несколько объявленных программных элементов доступны только в пределах сборки, содержащей их объявление.  
  
## <a name="remarks"></a>Remarks  

 Во многих случаях требуется, чтобы элементы программирования, такие как классы и структуры, использовались целой сборкой, а не только компонентом, который их объявляет. Однако может быть нежелательно, чтобы они были доступны коду за пределами сборки (например, если приложение является собственным). Если требуется ограничить доступ к элементу таким образом, его можно объявить с помощью `Friend` модификатора.  
  
 Код в других классах, структурах и модулях, компилируемых в одну и ту же сборку, может обращаться ко всем `Friend` элементам в этой сборке.  
  
 `Friend` доступ часто является предпочтительным уровнем для программных элементов приложения, а `Friend` также уровнем доступа по умолчанию для интерфейса, модуля, класса или структуры.  
  
 Можно использовать `Friend` только на уровне модуля, интерфейса или пространства имен. Таким образом, контекст объявления для `Friend` элемента должен быть исходным файлом, пространством имен, интерфейсом, модулем, классом или структурой. он не может быть процедурой.  

> [!NOTE]
> Можно также использовать модификатор доступа [Protected Friend](protected-friend.md) , который делает член класса доступным из этого класса, из производных классов и из той же сборки, в которой определен класс. Для ограничения доступа к члену из его класса и из производных классов в той же сборке используется модификатор [закрытого](private-protected.md) доступа.

 Сравнение `Friend` и других модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
> Можно указать, что другая сборка является дружественной, что позволяет ей получить доступ ко всем типам и членам, помеченным как `Friend` . Дополнительные сведения см. в разделе [Дружественные сборки](../../../standard/assembly/friend.md).

## <a name="example"></a>Пример  

 Следующий класс использует `Friend` модификатор, чтобы разрешить другим элементам программирования в той же сборке доступ к определенным элементам.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Использование  

 Модификатор можно использовать `Friend` в следующих контекстах:  
  
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
  
 [Property Statement](../statements/property-statement.md)  
  
 [Оператор Structure](../statements/structure-statement.md)  
  
 [Оператор Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Общедоступная](public.md)
- [Защищенный](protected.md)
- [Частная](private.md)
- [Частный защищенный](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
