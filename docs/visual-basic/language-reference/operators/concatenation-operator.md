---
title: Оператор &amp;
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 20c2e2088691e68221872cc1dfc5486413515a4d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867150"
---
# <a name="amp-operator-visual-basic"></a>&amp; Оператор (Visual Basic)

Формирует объединение строк двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Компоненты  

 `result`  
 Обязательный элемент. Любая `String` `Object` переменная или.  
  
 `expression1`  
 Обязательный элемент. Любое выражение с типом данных, которое расширяется до `String` .  
  
 `expression2`  
 Обязательный элемент. Любое выражение с типом данных, которое расширяется до `String` .  
  
## <a name="remarks"></a>Remarks  

 Если тип данных `expression1` или `expression2` не имеет значение `String` , а расширяется до `String` , то он преобразуется в `String` . Если один из типов данных не расширяется до `String` , компилятор выдает ошибку.  
  
 Тип данных `result` — `String` . Если одно или оба выражения имеют значение [Nothing](../nothing.md) или не имеют значения <xref:System.DBNull.Value?displayProperty=nameWithType> , они обрабатываются как строка со значением "".  
  
> [!NOTE]
> `&`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Символ амперсанда (&) также можно использовать для задания переменных в качестве типа `Long` . Дополнительные сведения см. в разделе [символы типа](../../programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Пример  

 В этом примере `&` оператор используется для принудительного сцепления строк. Результатом является строковое значение, представляющее объединение двух строковых операндов.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [ Оператор&=](and-assignment-operator.md)
- [Операторы объединения](concatenation-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы объединения в Visual Basic](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
