---
title: Лямбда-выражения недопустимы в первом выражении оператора Select Case
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 08f7cd9dd95a10cad0df6539ba43122495347bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397367"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>Лямбда-выражения недопустимы в первом выражении оператора Select Case
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
  
## <a name="see-also"></a>См. также раздел

- [Лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Оператор If…Then…Else](../statements/if-then-else-statement.md)
- [Оператор Select…Case](../statements/select-case-statement.md)
