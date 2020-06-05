---
title: Переопределения
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392032"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)

Указывает, что свойство или процедура переопределяет свойство или процедуру с идентичным названием, унаследованную от базового класса.

## <a name="rules"></a>Правила

- **Контекст объявления.** Можно использовать `Overrides` только в операторе объявления свойства или процедуры.

- **Комбинированные модификаторы.** Нельзя указывать `Overrides` вместе с `Shadows` или `Shared` в одном объявлении. Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.

- **Соответствие сигнатур.** Сигнатура этого объявления должна точно совпадать с *сигнатурой* свойства или процедуры, которую он переопределяет. Это означает, что списки параметров должны содержать одинаковое число параметров, в том же порядке и с теми же типами данных.

  Помимо сигнатуры, для объявления переопределения должны также совпадать следующие элементы:

  - уровень доступа;

  - тип возвращаемого значения (если применимо).

- **Универсальные сигнатуры.** Для универсальной процедуры сигнатура содержит число параметров типа. Поэтому объявление переопределения должно соответствовать версии базового класса и в этом аспекте.

- **Дополнительные соответствия.** Помимо соответствия сигнатуры версии базового класса, это объявление должно также соответствовать ему в следующих аспектах:

  - Модификатор уровня доступа (например, [Public](public.md))

  - Механизм передачи каждого параметра ([ByVal](byval.md) или [ByRef](byref.md))

  - списки ограничений для каждого типа параметра универсальной процедуры.

- **Сокрытие и переопределение.** Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).

При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.

Модификатор `Overrides` можно использовать в следующих контекстах:

- [Оператор Function](../statements/function-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Оператор Sub](../statements/sub-statement.md)

## <a name="see-also"></a>См. также раздел

- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Overridable](overridable.md)
- [Ключевые слова](../keywords/index.md)
- [Сокрытие в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
