---
description: Дополнительные сведения о новом операторе (Visual Basic)
title: Оператор New
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: f52dd7606127c7587173de8a78e618ceb3e4681d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665384"
---
# <a name="new-operator-visual-basic"></a>Оператор New (Visual Basic)

Вводит `New` предложение для создания нового экземпляра объекта, задает ограничение конструктора для параметра типа или определяет `Sub` процедуру как конструктор класса.

## <a name="remarks"></a>Remarks

В объявлении или операторе присваивания в `New` предложении необходимо указать определенный класс, из которого можно создать экземпляр. Это означает, что класс должен предоставлять один или несколько конструкторов, к которым вызывающий код может получить доступ.

Предложение можно использовать `New` в операторе объявления или в операторе присваивания. При выполнении инструкции вызывается соответствующий конструктор указанного класса, передавая все предоставленные аргументы. В следующем примере демонстрируется создание экземпляров `Customer` класса, который имеет два конструктора, один из которых не принимает параметры и один принимает строковый параметр:

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

Поскольку массивы являются классами, `New` может создать новый экземпляр массива, как показано в следующем примере:

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

Среда CLR выдает <xref:System.OutOfMemoryException> ошибку, если недостаточно памяти для создания нового экземпляра.

> [!NOTE]
> `New`Ключевое слово также используется в списках параметров типов, чтобы указать, что предоставленный тип должен предоставлять доступный конструктор без параметров. Дополнительные сведения о параметрах типа и ограничениях см. в разделе [Type List](../statements/type-list.md).

Чтобы создать процедуру конструктора для класса, задайте в качестве имени `Sub` процедуры `New` ключевое слово. Дополнительные сведения см. в разделе [время существования объекта: как создаются и уничтожаются объекты](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

Ключевое слово `New` можно использовать в следующих контекстах:

- [Оператор Dim](../statements/dim-statement.md)
- [Окна](../statements/of-clause.md)
- [Оператор Sub](../statements/sub-statement.md)

## <a name="see-also"></a>См. также

- <xref:System.OutOfMemoryException>
- [Ключевые слова](../keywords/index.md)
- [Type List](../statements/type-list.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Время существования: создание и уничтожение объектов](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
