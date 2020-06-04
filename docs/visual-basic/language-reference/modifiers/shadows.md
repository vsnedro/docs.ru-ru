---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 7aed6bec21bd484cca019b061bd5915de13a9eb8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402711"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Указывает, что объявленный программный элемент повторно объявляет и скрывает элемент с идентичным именем или набор перегруженных элементов в базовом классе.

## <a name="remarks"></a>Комментарии

Основное назначение теневого копирования (которое также называется *скрытием по имени*) — сохранение определения членов класса. Базовый класс может быть подвергнут изменениям, создающим элемент с тем же именем, что и у уже определенного. В этом случае `Shadows` Модификатор принудительно определяет ссылки через класс на определенный член, а не на новый элемент базового класса.

Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Правила

- **Контекст объявления.** Можно использовать `Shadows` только на уровне класса. Это означает, что контекст объявления для `Shadows` элемента должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.

  В одном операторе объявления можно объявить только один элемент с тенью.

- **Комбинированные модификаторы.** Нельзя указывать `Shadows` вместе с `Overloads` , `Overrides` или `Static` в одном объявлении.

- **Типы элементов.** Можно скрыть любой тип объявленного элемента, используя любой другой тип. При скрытии свойства или процедуры с другим свойством или процедурой параметры и тип возвращаемого значения не должны совпадать с параметрами в свойстве или процедуре базового класса.

- **Данному.** Затененный элемент в базовом классе обычно недоступен в производном классе, который его затеняет. Однако применимы следующие рекомендации.

  - Если элемент теневого копирования недоступен из кода, ссылающегося на него, ссылка разрешается в затененный элемент. Например, если `Private` элемент затеняет элемент базового класса, код, который не имеет разрешения на доступ к `Private` элементу, обращается к элементу базового класса.

  - При скрытии элемента доступ к затененному элементу по-прежнему можно получить через объект, объявленный с типом базового класса. Доступ к нему также можно получить с помощью `MyBase` .

Модификатор `Shadows` можно использовать в следующих контекстах:

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

- [Общий](shared.md)
- [Статическое](static.md)
- [Частное](private.md)
- [Me, My, MyBase и MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Перегрузки](overloads.md)
- [Overridable](overridable.md)
- [Переопределения](overrides.md)
- [Сокрытие в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
