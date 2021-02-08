---
description: 'Дополнительные сведения о: BC36635: лямбда-выражения недопустимы в первом выражении оператора Select Case'
title: Лямбда-выражения недопустимы в первом выражении оператора Select Case
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: e0c388db7164f6c9f99ba917109593a796f7b23b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795941"
---
# <a name="bc36635-lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>BC36635: лямбда-выражения недопустимы в первом выражении оператора Select Case

Нельзя использовать лямбда-выражение для тестового выражения в `Select Case` инструкции. Определения лямбда-выражений возвращают функции, а тестовое выражение `Select Case` инструкции должно иметь простейший тип данных.

 Следующий код вызывает эту ошибку:

```vb
' Select Case (Function(arg) arg Is Nothing)
    ' List of the cases.
' End Select
```

 **Идентификатор ошибки:** BC36635

## <a name="to-correct-this-error"></a>Исправление ошибки

- Проверьте свой код, чтобы определить, подойдет ли вам другая условная конструкция, например оператор `If...Then...Else` .

- Возможно, вы предполагали вызвать функцию, как показано в следующем коде:

```vb
Dim num? As Integer
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))
    ' List of the cases
End Select
```

## <a name="see-also"></a>См. также

- [Лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Оператор If…Then…Else](../statements/if-then-else-statement.md)
- [Оператор Select…Case](../statements/select-case-statement.md)
