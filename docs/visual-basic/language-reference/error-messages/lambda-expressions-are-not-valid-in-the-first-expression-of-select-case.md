---
title: Лямбда-выражения недопустимы в первом выражении оператора Select Case
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 448a685a7c174ce212389842c31066f1c4557cdf
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162535"
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
