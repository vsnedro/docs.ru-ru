---
description: 'Дополнительные сведения о: BC32098: параметры типа нельзя использовать в качестве квалификаторов'
title: Параметры типа нельзя использовать в качестве квалификаторов
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 61be8e81c9cf6c7a8339c7bbf0ad9566f582eb57
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675056"
---
# <a name="bc32098-type-parameters-cannot-be-used-as-qualifiers"></a>BC32098: параметры типа не могут использоваться в качестве квалификаторов

Элемент программирования дополняется уточняющей строкой, включающей параметр типа.

Параметр типа представляет требование для типа, который должен предоставляться при создании универсального типа. Он не представляет определенный определенный тип. Уточняющая строка должна включать только те элементы, которые определены во время компиляции.

Следующий код может вызвать эту ошибку:

```vb
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean

    Dim saveText As c.Text
    ' Insert code to look for badText within saveText.
End Function
```

 **Идентификатор ошибки:** BC32098

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Удалите параметр типа из строки квалификации или замените его определенным типом.

2. Если необходимо использовать сконструированный тип для нахождение квалифицированного программного элемента, необходимо использовать дополнительную логику программы.

## <a name="see-also"></a>См. также

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
