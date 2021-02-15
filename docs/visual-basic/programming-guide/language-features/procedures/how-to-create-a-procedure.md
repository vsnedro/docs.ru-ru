---
description: Дополнительные сведения о том, как создать процедуру (Visual Basic).
title: Практическое руководство. Создание процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: bca5ad24e845600642429273f6053787dd290b88
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472544"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Практическое руководство. Создание процедуры (Visual Basic)

Процедура заключается в заключении между операторами начального объявления ( `Sub` или `Function` ) и завершающим оператором объявления ( `End Sub` или `End Function` ). Весь код процедуры находится между этими операторами.

 Процедура не может содержать другую процедуру, поэтому ее начальные и конечные операторы должны находиться за пределами любой другой процедуры.

 Если у вас есть код, выполняющий одну и ту же задачу в разных местах, можно написать задачу один раз как процедуру, а затем вызвать ее из различных мест в коде.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Создание процедуры, которая не возвращает значение

1. За пределами любой другой процедуры используйте `Sub` оператор, за которым следует `End Sub` оператор.

2. В `Sub` инструкции используйте `Sub` ключевое слово с именем процедуры, а затем список параметров в круглых скобках.

3. Поместите операторы кода процедуры между `Sub` `End Sub` операторами и.

### <a name="to-create-a-procedure-that-returns-a-value"></a>Создание процедуры, возвращающей значение

1. За пределами любой другой процедуры используйте `Function` оператор, за которым следует `End Function` оператор.

2. В `Function` инструкции используйте `Function` ключевое слово с именем процедуры, затем список параметров в круглых скобках, а затем `As` предложение, указывающее тип данных возвращаемого значения.

3. Поместите операторы кода процедуры между `Function` `End Function` операторами и.

4. Используйте `Return` оператор, чтобы вернуть значение в вызывающий код.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Подключение новой процедуры к старым и повторяющимся блокам кода

1. Убедитесь, что вы определили новую процедуру в том месте, где старый код имеет к ней доступ.

2. В старом и повторяющемся блоке кода замените инструкции, выполняющие повторяющуюся задачу, на одну инструкцию, которая вызывает `Sub` `Function` процедуру или.

3. Если процедура `Function` возвращает значение, убедитесь, что вызывающая инструкция выполняет действие с возвращаемым значением, например, сохраняя его в переменной, или, в противном случае, значение будет потеряно.

## <a name="example"></a>Пример

 Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон:

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a>См. также раздел

- [Процедуры](index.md)
- [Подпрограммы](sub-procedures.md)
- [Процедуры функций](function-procedures.md)
- [Процедуры свойств](property-procedures.md)
- [Процедуры операторов](operator-procedures.md)
- [Параметры и аргументы процедуры](procedure-parameters-and-arguments.md)
- [Рекурсивные процедуры](recursive-procedures.md)
- [Перегрузка процедур](procedure-overloading.md)
- [Объекты и классы](../objects-and-classes/index.md)
- [Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)
