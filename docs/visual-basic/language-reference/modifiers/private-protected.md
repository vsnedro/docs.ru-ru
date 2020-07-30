---
title: Частный защищенный
ms.date: 05/10/2018
f1_keywords:
- vb.PrivateProtected
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 8ad1509da71bc80b33700d363ddd4569a0965dff
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303469"
---
# <a name="private-protected-visual-basic"></a>Частный защищенный (Visual Basic)

Комбинация ключевых слов `Private Protected` является модификатором доступа к члену. `Private Protected`Элемент доступен для всех элементов в содержащем его классе, а также по типам, производным от содержащего класса, но только в том случае, если они находятся в содержащей его сборке.

Можно указать `Private Protected` только для членов классов. нельзя применять `Private Protected` к членам структуры, поскольку структуры не наследуются.

`Private Protected`Модификатор доступа поддерживается Visual Basic 15,5 и более поздних версий. Чтобы использовать его, можно добавить в файл проекта Visual Basic (VBPROJ) следующий элемент \* . Если в системе установлен Visual Basic 15,5 или более поздней версии, он позволяет воспользоваться всеми возможностями языка, поддерживаемыми последней версией компилятора Visual Basic.

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Дополнительные сведения см. [в разделе Задание языковой версии Visual Basic](../configure-language-version.md).

> [!NOTE]
> В Visual Studio выбор справки F1 `private protected` для предоставляет справку как для [частного](private.md) , так и для [защищенного](protected.md). Интегрированная среда разработки выбирает один маркер под курсором, а не составное слово.

## <a name="rules"></a>Правила

- **Контекст объявления.** Можно использовать `Private Protected` только на уровне класса. Это означает, что контекст объявления для `Protected` элемента должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.

## <a name="behavior"></a>Поведение

- **Уровень доступа.** Весь код в классе может обращаться к его элементам. Код в любом классе, производном от базового класса и содержащийся в той же сборке, имеет доступ ко всем `Private Protected` элементам базового класса. Однако код в любом классе, производном от базового класса и содержащийся в другой сборке, не может получить доступ к элементам базового класса `Private Protected` .

- **Модификаторы доступа.** Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*. Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Модификатор `Private Protected` можно использовать в следующих контекстах:

- [Оператор Class](../statements/class-statement.md) вложенного класса

- [Оператор Const](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Оператор Delegate](../statements/delegate-statement.md) делегата, вложенного в класс

- [Оператор Dim](../statements/dim-statement.md)

- [Оператор Enum](../statements/enum-statement.md) перечисления, вложенного в класс

- [Оператор Event](../statements/event-statement.md)

- [Оператор Function](../statements/function-statement.md)

- [Оператор Interface](../statements/interface-statement.md) интерфейса, вложенного в класс

- [Property Statement](../statements/property-statement.md)

- [Оператор Structure](../statements/structure-statement.md) структуры, вложенной в класс

- [Оператор Sub](../statements/sub-statement.md)

## <a name="see-also"></a>См. также

- [Открытый](public.md)
- [От](protected.md)
- [Объявление](friend.md)
- [Частное](private.md)
- [Protected Friend](./protected-friend.md)
- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
