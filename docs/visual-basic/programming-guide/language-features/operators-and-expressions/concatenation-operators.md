---
title: Операторы объединения
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: c123438a86a2c3293a99770107d970535fcdbdf8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388794"
---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="fcaa7-102">Операторы объединения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcaa7-102">Concatenation Operators in Visual Basic</span></span>

<span data-ttu-id="fcaa7-103">Операторы объединения объединяют несколько строк в одну.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="fcaa7-104">Существует два оператора объединения: `+` и `&`.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="fcaa7-105">Оба они выполняют базовую операцию объединения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>

```vb
Dim x As String = "Mic" & "ro" & "soft"
Dim y As String = "Mic" + "ro" + "soft"
' The preceding statements set both x and y to "Microsoft".
```

<span data-ttu-id="fcaa7-106">Эти операторы также могут объединять переменные `String`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>

[!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]

## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="fcaa7-107">Различия между двумя операторами объединения</span><span class="sxs-lookup"><span data-stu-id="fcaa7-107">Differences Between the Two Concatenation Operators</span></span>

<span data-ttu-id="fcaa7-108">[Оператор +](../../../language-reference/operators/addition-operator.md) имеет основную цель сложения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-108">The [+ Operator](../../../language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="fcaa7-109">Однако он также может объединять числовые операнды со строковыми.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-109">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="fcaa7-110">Оператор `+` имеет сложный набор правил, определяющий, следует ли выполнять добавление, объединение, сигнализировать об ошибке компилятора или выдавать исключение времени выполнения <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-110">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="fcaa7-111">[Оператор&](../../../language-reference/operators/concatenation-operator.md) определен только для `String` операндов и всегда расширяет его операнды до `String` , независимо от значения параметра `Option Strict` .</span><span class="sxs-lookup"><span data-stu-id="fcaa7-111">The [& Operator](../../../language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="fcaa7-112">Оператор `&` рекомендуется использовать для объединения строк, так как он определен исключительно для строк и снижает шансы создания непреднамеренного преобразования.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-112">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>

## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="fcaa7-113">Производительность: String и StringBuilder</span><span class="sxs-lookup"><span data-stu-id="fcaa7-113">Performance: String and StringBuilder</span></span>

<span data-ttu-id="fcaa7-114">Если вы выполняете множество операций со строкой, таких как объединения, удаления и замены, использование класса <xref:System.Text.StringBuilder> из пространства имен <xref:System.Text> может оказать положительное влияние на производительность.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-114">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="fcaa7-115">Для создания и инициализации объекта <xref:System.Text.StringBuilder> требуется дополнительная инструкция, кроме того, еще одна инструкция необходима для преобразования итогового значения в `String`, однако это время можно скомпенсировать высокой скоростью выполнения <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-115">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcaa7-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fcaa7-116">See also</span></span>

- [<span data-ttu-id="fcaa7-117">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="fcaa7-117">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="fcaa7-118">Типы методов для работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcaa7-118">Types of String Manipulation Methods in Visual Basic</span></span>](../strings/types-of-string-manipulation-methods.md)
- [<span data-ttu-id="fcaa7-119">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcaa7-119">Arithmetic Operators in Visual Basic</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="fcaa7-120">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcaa7-120">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="fcaa7-121">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcaa7-121">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
