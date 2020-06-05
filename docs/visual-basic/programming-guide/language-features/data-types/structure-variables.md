---
title: Переменные структуры
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 270e8ca26185e4a68def3b95f4ce6ab4c57a629c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393589"
---
# <a name="structure-variables-visual-basic"></a>Переменные структуры (Visual Basic)

После создания структуры можно объявить переменные уровня процедуры и модуля в качестве этого типа. Например, можно создать структуру, которая записывает сведения о компьютерной системе. Это продемонстрировано в следующем примере.

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

Теперь можно объявлять переменные этого типа. Это показано в следующем объявлении.

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> В классах и модулях структуры, объявленные с помощью [инструкции Dim](../../../language-reference/statements/dim-statement.md) , по умолчанию имеют открытый доступ. Если структура должна быть закрытой, убедитесь, что она объявлена с помощью ключевого слова [Private](../../../language-reference/modifiers/private.md) .

## <a name="access-to-structure-values"></a>Доступ к значениям структуры

Для присвоения и извлечения значений из элементов переменной структуры используется тот же синтаксис, что и при использовании для задания и получения свойств объекта. Оператор доступа к членам () размещается `.` между именем переменной структуры и именем элемента. В следующем примере осуществляется доступ к элементам переменных, ранее объявленных как тип `systemInfo` .

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a>Присваивание переменных структуры

Можно также присвоить одну переменную другой, если оба имеют один и тот же тип структуры. Все элементы одной структуры копируются в соответствующие элементы в другом. Это показано в следующем объявлении.

```vb
yourSystem = mySystem
```

Если элемент структуры является ссылочным типом, таким как массив типа `String` , `Object` или, то копируется указатель на данные. В предыдущем примере, если `systemInfo` была включена объектная переменная, в предыдущем примере был скопирован указатель из `mySystem` в `yourSystem` , а изменение данных объекта через одну структуру вступит в действие при доступе через другую структуру.

## <a name="see-also"></a>См. также раздел

- [Типы данных](index.md)
- [Простые типы данных](elementary-data-types.md)
- [Составные типы данных](composite-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Структуры](structures.md)
- [Устранение неполадок, связанных с типами данных](troubleshooting-data-types.md)
- [Практическое руководство. Объявление структуры](how-to-declare-a-structure.md)
- [Структуры и другие элементы программирования](structures-and-other-programming-elements.md)
- [Структуры и классы](structures-and-classes.md)
- [Оператор Structure](../../../language-reference/statements/structure-statement.md)
