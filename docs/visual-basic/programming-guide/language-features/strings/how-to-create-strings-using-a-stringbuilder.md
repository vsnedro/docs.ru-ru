---
description: Дополнительные сведения см. в статье как создавать строки с помощью StringBuilder в Visual Basic
title: Инструкции. Создание строк с помощью StringBuilder
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 6def32517f71ec3c2a7795c3395e3e572903ce1e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429823"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Инструкции. Создание строк с помощью StringBuilder в Visual Basic

В этом примере создается длинная строка из множества меньших строк с помощью <xref:System.Text.StringBuilder> класса. <xref:System.Text.StringBuilder>Класс является более эффективным, чем `&=` оператор для сцепления многих строк.

## <a name="example"></a>Пример

В следующем примере создается экземпляр <xref:System.Text.StringBuilder> класса, добавляются строки 1 000 в этот экземпляр, а затем возвращается его строковое представление:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>См. также раздел

- [Using the StringBuilder class](../../../../standard/base-types/stringbuilder.md) (Использование класса StringBuilder)
- [ Оператор&=](../../../language-reference/operators/and-assignment-operator.md)
- [Строки](index.md)
- [Создание строк](../../../../standard/base-types/creating-new.md)
- [Операции со строками](../../../../standard/base-types/best-practices-strings.md)
