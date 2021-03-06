---
title: Ожидается инициализатор
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: cbe77bab3e4f8bf2094c70c1c16d95ee897c729e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163016"
---
# <a name="bc30996-initializer-expected"></a>BC30996: требуется инициализатор

Предпринята попытка объявить экземпляр класса с помощью инициализатора объекта, в котором список инициализации пуст, как показано в следующем примере.

 `' Not valid.`

 `' Dim aStudent As New Student With {}`

 В списке инициализаторов должно быть инициализировано по крайней мере одно поле или свойство, как показано в следующем примере.

 `Dim aStudent As New Student With {.year = "Senior"}`

 **Идентификатор ошибки:** BC30996

## <a name="to-correct-this-error"></a>Исправление ошибки

- Инициализируйте по крайней мере одно поле или свойство в инициализаторе или не используйте инициализатор объекта.

## <a name="see-also"></a>См. также

- [Инициализаторы объектов: именованные и анонимные типы](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
