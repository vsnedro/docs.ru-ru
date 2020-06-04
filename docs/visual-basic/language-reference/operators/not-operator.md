---
title: Оператор Not
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 56cdeb80a217dbce15921eddd6a43d8d1b049376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401463"
---
# <a name="not-operator-visual-basic"></a>Оператор Not (Visual Basic)
Выполняет логическое отрицание `Boolean` выражения или побитовое отрицание в числовом выражении.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>Компоненты  
 `result`  
 Обязательный. Произвольное выражение типа `Boolean` или числового типа.  
  
 `expression`  
 Обязательный. Произвольное выражение типа `Boolean` или числового типа.  
  
## <a name="remarks"></a>Комментарии  
 Для `Boolean` выражений в следующей таблице показано, как `result` определяется.  
  
|Если `expression` имеет значение |Значение `result` равно|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Для числовых выражений `Not` оператор инвертирует битовые значения любого числового выражения и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.  
  
|Если бит в `expression` имеет значение|Бит в `result` имеет значение|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Для логического отрицания тип данных результата — `Boolean` . Для побитового отрицания тип данных результата такой же, как и у `expression` . Однако если выражение имеет значение `Decimal` , результатом будет `Long` .  
  
## <a name="overloading"></a>Перегрузка  
 `Not`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если его операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `Not` для выполнения логического отрицания в `Boolean` выражении. Результатом является `Boolean` значение, представляющее обратную величину значения выражения.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 В предыдущем примере создаются результаты `False` и `True` соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `Not` для выполнения логического отрицания отдельных битов числового выражения. Бит в результирующем шаблоне имеет значение, противоположное соответствующему биту в шаблоне операнда, включая бит знака.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 В предыдущем примере создаются результаты – 11, – 9 и – 7 соответственно.  
  
## <a name="see-also"></a>См. также раздел

- [Логические (побитовые) операторы (Visual Basic)](logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Логические и побитовые операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
