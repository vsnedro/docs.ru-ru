---
description: 'Дополнительные сведения о: BC30996: требуется инициализатор'
title: Ожидается инициализатор
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: a9859dc319ec53cb42785d71b21447a097ce30f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796058"
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
