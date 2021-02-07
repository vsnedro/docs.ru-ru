---
description: 'Дополнительные сведения о: Protected Friend (Visual Basic)'
title: Protected Friend
ms.date: 05/10/2018
f1_keywords:
- vb.ProtectedFriend
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: dcc8fd2b1aa99f910f002ac05178d379532fb73d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700979"
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

Комбинация ключевых слов `Protected Friend` является модификатором доступа к члену. Он предоставляет [дружественный](friend.md) доступ и [защищенный](protected.md) доступ к объявленным элементам, поэтому они доступны из любого места в одной сборке, из их собственного класса и из производных классов. Можно указать `Protected Friend` только для членов классов. нельзя применять `Protected Friend` к членам структуры, поскольку структуры не наследуются.

> [!NOTE]
> В Visual Studio выберите Справка F1 в справке `protected friend` для [защищенного](protected.md) или [дружественного](friend.md)доступа. Интегрированная среда разработки выбирает один маркер под курсором, а не составное слово.

## <a name="rules"></a>Правила

**Контекст объявления.** Можно использовать `Protected Friend` только на уровне класса. Это означает, что контекст объявления для `Protected` элемента должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.

## <a name="see-also"></a>См. также

- [Общедоступная](public.md)
- [Защищенный](protected.md)
- [Friend](friend.md)
- [Частная](private.md)
- [Частный защищенный](./private-protected.md)
- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
