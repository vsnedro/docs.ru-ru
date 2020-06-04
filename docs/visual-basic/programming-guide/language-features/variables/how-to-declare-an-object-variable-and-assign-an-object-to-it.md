---
title: Практическое руководство. Объявление объектной переменной и присвоение ей объекта
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: d9a8c1fb30bfa5988d48202e41202e7ede0f5f27
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410507"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта

Переменная [типа данных Object](../../../language-reference/data-types/object-data-type.md) объявляется путем указания `As Object` в [операторе Dim](../../../language-reference/statements/dim-statement.md). Вы назначаете объект такой переменной, помещая объект после знака равенства ( `=` ) в операторе присваивания или предложении инициализации.

## <a name="example"></a>Пример

В следующем примере объявляется `Object` переменная и назначается ей текущий экземпляр.

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

Объявление и присваивание можно объединить, инициализируя переменную как часть ее объявления. Следующий пример эквивалентен предыдущему примеру.

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a>Компиляция кода

Для этого примера требуются:

- ссылка на пространство имен <xref:System>.

- Класс, структура или модуль, в котором будет размещена `Dim` инструкция.

- Процедура, в которой следует разместить оператор присваивания.

## <a name="see-also"></a>См. также раздел

- [Объявление переменной](variable-declaration.md)
- [Объектные переменные](object-variables.md)
- [Объявление объектной переменной](object-variable-declaration.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Оператор Dim](../../../language-reference/statements/dim-statement.md)
- [Вывод локального типа](local-type-inference.md)
- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
