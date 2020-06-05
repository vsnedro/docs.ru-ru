---
title: Практическое руководство. Хранение нескольких значений в переменной
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 399c5909ee6988f96bcc85260b0401f3bd18a0f2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393900"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Практическое руководство. Хранение нескольких значений в переменной (Visual Basic)

Переменная содержит более одного значения, если объявить ее для *составного типа данных*.

[Составные типы данных](composite-data-types.md) включают структуры, массивы и классы. Переменная составного типа данных может содержать сочетание простейших типов данных и других составных типов. Структуры и классы могут содержать код и данные.

## <a name="to-hold-more-than-one-value-in-a-variable"></a>Хранение более одного значения в переменной

1. Определите составной тип данных, который будет использоваться для переменной.

2. Если составной тип данных еще не определен, определите его, чтобы переменная могла его использовать.

    - Определите структуру с помощью [оператора Structure](../../../language-reference/statements/structure-statement.md).

    - Определите массив с помощью [оператора Dim](../../../language-reference/statements/dim-statement.md).

    - Определите класс с помощью [оператора класса](../../../language-reference/statements/class-statement.md).

3. Объявите переменную с помощью `Dim` оператора.

4. Подпишите имя переменной с помощью `As` предложения.

5. Используйте `As` ключевое слово с именем соответствующего составного типа данных.

## <a name="see-also"></a>См. также раздел

- [Типы данных](../../../language-reference/data-types/index.md)
- [Символы типов](type-characters.md)
- [Составные типы данных](composite-data-types.md)
- [Структуры](structures.md)
- [Массивы](../arrays/index.md)
- [Объекты и классы](../objects-and-classes/index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
