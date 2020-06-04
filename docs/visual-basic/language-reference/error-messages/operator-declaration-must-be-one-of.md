---
title: 'Объявление оператора должно быть одним из следующих: +,-, *,-,-, ^, &amp; , Like, mod, and, или, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 3fb2cf392611e5ca83818e3bf173513be031085d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409339"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>Объявление оператора должно быть одним из следующих: +,-, *, \, /, ^, &amp; , Like, mod, and, или, XOR, not, \<\<, >>...
Можно объявить только оператор, пригодный для перегрузки. В следующей таблице перечислены операторы, которые можно объявить.  
  
|Тип|Операторы|  
|----------|---------------|  
|Унарный|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Двоичный|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Преобразование (унарный)|`CType`|  
  
 Обратите внимание, что `=` оператор в списке binary является оператором сравнения, а не оператором присваивания.  
  
 **Идентификатор ошибки:** BC33000  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Выберите оператор из набора перегружаемых операторов.  
  
2. Если требуется возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте процедуру `Function` , которая принимает соответствующие параметры и возвращает соответствующее значение.  
  
## <a name="see-also"></a>См. также раздел

- [Operator Statement](../statements/operator-statement.md)
- [Процедуры операторов](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Практическое руководство. Определение оператора](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Оператор Function](../statements/function-statement.md)
