---
description: 'Дополнительные сведения: расширение (Visual Basic)'
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: de290296ba2b7716ba992c6bed46443053048282
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700706"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)

Указывает, что оператор преобразования ( `CType` ) преобразует класс или структуру в тип, который может содержать все возможные значения исходного класса или структуры.  
  
## <a name="converting-with-the-widening-keyword"></a>Преобразование с помощью ключевого слова Widening  

 Процедура преобразования должна указываться `Public Shared` в дополнение к `Widening` .  
  
 Расширяющие преобразования всегда выполняются в период выполнения и никогда не вызывают потери данных. Примеры: `Single` `Double` , `Char` до `String` и производный тип в его базовом типе. Последнее преобразование является расширяющим, так как производный тип содержит все члены базового типа и, таким же, является экземпляром базового типа.  
  
 Этот код не обязательно должен использоваться `CType` для расширяющих преобразований, даже если `Option Strict` имеет значение `On` .  
  
 `Widening`Ключевое слово можно использовать в следующем контексте:  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 Примеры определений расширяющих и суженных операторов преобразования см. в разделе [руководство. Определение оператора преобразования](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>См. также

- [Operator Statement](../statements/operator-statement.md)
- [Narrowing](narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Практическое руководство. Определение оператора](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Оператор Option Strict](../statements/option-strict-statement.md)
- [Практическое руководство. Определение оператора преобразования](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
