---
title: Защищенный
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: d66ed68004f8b6ef21ae703f02b317589814764b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398224"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)

Модификатор доступа к члену, указывающий, что один или несколько объявленных программных элементов доступны только в своем собственном классе или производном классе.

## <a name="remarks"></a>Комментарии

Иногда программный элемент, объявленный в классе, содержит конфиденциальные данные или ограниченный код и требуется ограничить доступ к элементу. Однако если класс является наследуемым и предполагается иерархия производных классов, то эти производные классы могут быть необходимы для доступа к данным или коду в этих производных классах. В этом случае необходимо, чтобы элемент был доступен как из базового класса, так и из всех производных классов. Чтобы ограничить доступ к элементу таким образом, его можно объявить с помощью `Protected` .

> [!NOTE]
> `Protected`Модификатор доступа можно сочетать с двумя другими модификаторами:
>
> - Модификатор [Protected Friend](protected-friend.md) делает член класса доступным из этого класса, из производных классов и из той же сборки, в которой определен класс.
> - Модификатор [Private protected](private-protected.md) делает член класса доступным для производных типов, но только внутри его содержащей сборки.

## <a name="rules"></a>Правила

**Контекст объявления.** Можно использовать `Protected` только на уровне класса. Это означает, что контекст объявления для `Protected` элемента должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.

## <a name="behavior"></a>Поведение

- **Уровень доступа.** Весь код в классе может обращаться к его элементам. Код в любом классе, производном от базового класса, может обращаться ко всем `Protected` элементам базового класса. Это справедливо для всех поколений наследования. Это означает, что класс может обращаться к `Protected` элементам базового класса базового класса и т. д.

     Защищенный доступ не является надмножеством или подмножеством дружественного доступа.

- **Модификаторы доступа.** Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*. Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Модификатор `Protected` можно использовать в следующих контекстах:

- [Оператор Class](../statements/class-statement.md)

- [Оператор Const](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Оператор Delegate](../statements/delegate-statement.md)

- [Оператор Dim](../statements/dim-statement.md)

- [Оператор Enum](../statements/enum-statement.md)

- [Оператор Event](../statements/event-statement.md)

- [Оператор Function](../statements/function-statement.md)

- [Оператор Interface](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Оператор Structure](../statements/structure-statement.md)

- [Оператор Sub](../statements/sub-statement.md)

## <a name="see-also"></a>См. также раздел

- [Открытый](public.md)
- [Объявление](friend.md)
- [Частное](private.md)
- [Частный защищенный](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
