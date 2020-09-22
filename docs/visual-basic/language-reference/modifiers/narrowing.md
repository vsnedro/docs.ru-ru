---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867932"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)

Указывает, что оператор преобразования ( `CType` ) преобразует класс или структуру в тип, который не может содержать некоторые из возможных значений исходного класса или структуры.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Преобразование с помощью ключевого слова "Narrow"  

 Процедура преобразования должна указываться `Public Shared` в дополнение к `Narrowing` .  
  
 Сужающие преобразования не всегда выполняются успешно во время выполнения и могут привести к сбою или потери данных. Примерами `Long` являются `Integer` , `String` to `Date` и базовый тип для производного типа. Последнее преобразование является сужением, так как базовый тип может не содержать все члены производного типа и поэтому не является экземпляром производного типа.  
  
 Если `Option Strict` имеет значение `On` , то `CType` для всех сужающих преобразований код должен использовать.  
  
 `Narrowing`Ключевое слово можно использовать в следующем контексте:  
  
 [Operator Statement](../statements/operator-statement.md)  
  
## <a name="see-also"></a>См. также

- [Operator Statement](../statements/operator-statement.md)
- [Widening](widening.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Практическое руководство. Определение оператора](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Оператор Option Strict](../statements/option-strict-statement.md)
