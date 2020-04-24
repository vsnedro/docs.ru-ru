---
title: 'Как: создание строк с помощью StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645328"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Как: создать строки с помощью StringBuilder в Visual Basic

Этот пример строит длинную строку из <xref:System.Text.StringBuilder> многих меньших строк с помощью класса. Класс <xref:System.Text.StringBuilder> более эффективен, `&=` чем оператор для свертывания многих строк.

## <a name="example"></a>Пример

Следующий пример создает экземпляр <xref:System.Text.StringBuilder> класса, привязывает к этому экземпляру 1000 строк, а затем возвращает его представление строки:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>См. также раздел

- [Использование класса StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [&оператор](../../../language-reference/operators/and-assignment-operator.md)
- [Строки](index.md)
- [Создание строк](../../../../standard/base-types/creating-new.md)
- [Операции со строками](../../../../standard/base-types/best-practices-strings.md)
