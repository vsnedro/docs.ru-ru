---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 202d4f4a3a05a64ab1d74621268f28f6b55e8952
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404840"
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

Комбинация ключевых слов `Protected Friend` является модификатором доступа к члену. Он предоставляет [дружественный](friend.md) доступ и [защищенный](protected.md) доступ к объявленным элементам, поэтому они доступны из любого места в одной сборке, из их собственного класса и из производных классов. Можно указать `Protected Friend` только для членов классов. нельзя применять `Protected Friend` к членам структуры, поскольку структуры не наследуются.

> [!NOTE]
> В Visual Studio выберите Справка F1 в справке `protected friend` для [защищенного](protected.md) или [дружественного](friend.md)доступа. Интегрированная среда разработки выбирает один маркер под курсором, а не составное слово.

## <a name="rules"></a>Правила

**Контекст объявления.** Можно использовать `Protected Friend` только на уровне класса. Это означает, что контекст объявления для `Protected` элемента должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.

## <a name="see-also"></a>См. также раздел

- [Открытый](public.md)
- [От](protected.md)
- [Объявление](friend.md)
- [Частное](private.md)
- [Частный защищенный](./private-protected.md)
- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
