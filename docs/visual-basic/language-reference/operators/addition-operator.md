---
title: + Оператор
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: 6ae3feae6ecb63b82426f2aa69359625bbffcec8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372120"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e5efd-102">Оператор + (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5efd-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="e5efd-103">Складывает два числа или возвращает положительное значение числового выражения.</span><span class="sxs-lookup"><span data-stu-id="e5efd-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="e5efd-104">Также можно использовать для сцепления двух строковых выражений.</span><span class="sxs-lookup"><span data-stu-id="e5efd-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5efd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5efd-105">Syntax</span></span>  
  
```vb
expression1 + expression2
```
  
<span data-ttu-id="e5efd-106">or</span><span class="sxs-lookup"><span data-stu-id="e5efd-106">or</span></span>

```vb  
+expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="e5efd-107">Компоненты</span><span class="sxs-lookup"><span data-stu-id="e5efd-107">Parts</span></span>  
  
|<span data-ttu-id="e5efd-108">Термин</span><span class="sxs-lookup"><span data-stu-id="e5efd-108">Term</span></span>|<span data-ttu-id="e5efd-109">Определение</span><span class="sxs-lookup"><span data-stu-id="e5efd-109">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="e5efd-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e5efd-110">Required.</span></span> <span data-ttu-id="e5efd-111">Любое числовое или строковое выражение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-111">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="e5efd-112">Требуется, если `+` оператор не вычисляет отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-112">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="e5efd-113">Любое числовое или строковое выражение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-113">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="e5efd-114">Результат</span><span class="sxs-lookup"><span data-stu-id="e5efd-114">Result</span></span>  
 <span data-ttu-id="e5efd-115">Если `expression1` и `expression2` являются числовыми, результатом является их арифметическая сумма.</span><span class="sxs-lookup"><span data-stu-id="e5efd-115">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="e5efd-116">Если параметр отсутствует `expression2` , `+` оператор является *унарным* оператором идентификации для неизменного значения выражения.</span><span class="sxs-lookup"><span data-stu-id="e5efd-116">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="e5efd-117">В этом смысле операция состоит из удержания знака `expression1` , поэтому результат будет отрицательным, если `expression1` имеет отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-117">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="e5efd-118">Если `expression1` и `expression2` являются строками, результатом является объединение их значений.</span><span class="sxs-lookup"><span data-stu-id="e5efd-118">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="e5efd-119">Если `expression1` и `expression2` имеют смешанные типы, то выполняемое действие зависит от их типов, их содержимого и значения, установленного в [операторе Option](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e5efd-119">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="e5efd-120">Дополнительные сведения см. в таблицах в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="e5efd-120">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="e5efd-121">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="e5efd-121">Supported Types</span></span>  
 <span data-ttu-id="e5efd-122">Все числовые типы, включая неподписанные и типы с плавающей запятой `Decimal` , и `String` .</span><span class="sxs-lookup"><span data-stu-id="e5efd-122">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5efd-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e5efd-123">Remarks</span></span>  
 <span data-ttu-id="e5efd-124">Как правило, `+` выполняет арифметическое сложение, когда это возможно, и объединяет только в том случае, если оба выражения являются строками.</span><span class="sxs-lookup"><span data-stu-id="e5efd-124">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="e5efd-125">Если ни одно из выражений не является `Object` , Visual Basic выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e5efd-125">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="e5efd-126">Типы данных выражений</span><span class="sxs-lookup"><span data-stu-id="e5efd-126">Data types of expressions</span></span>|<span data-ttu-id="e5efd-127">Действие по компилятору</span><span class="sxs-lookup"><span data-stu-id="e5efd-127">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="e5efd-128">Оба выражения являются числовыми типами данных ( `SByte` ,, `Byte` ,, `Short` `UShort` `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` или `Double` ).</span><span class="sxs-lookup"><span data-stu-id="e5efd-128">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="e5efd-129">Добавить.</span><span class="sxs-lookup"><span data-stu-id="e5efd-129">Add.</span></span> <span data-ttu-id="e5efd-130">Тип данных result является числовым типом, подходящим для типов данных `expression1` и `expression2` .</span><span class="sxs-lookup"><span data-stu-id="e5efd-130">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="e5efd-131">См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="e5efd-131">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="e5efd-132">Оба выражения имеют тип`String`</span><span class="sxs-lookup"><span data-stu-id="e5efd-132">Both expressions are of type `String`</span></span>|<span data-ttu-id="e5efd-133">Объединения.</span><span class="sxs-lookup"><span data-stu-id="e5efd-133">Concatenate.</span></span>|  
|<span data-ttu-id="e5efd-134">Одно выражение является числовым типом данных, а второй — строкой</span><span class="sxs-lookup"><span data-stu-id="e5efd-134">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="e5efd-135">Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="e5efd-135">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e5efd-136">Если `Option Strict` имеет значение `Off` , то неявно преобразует в `String` `Double` и добавьте.</span><span class="sxs-lookup"><span data-stu-id="e5efd-136">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="e5efd-137">Если `String` не удается преобразовать в `Double` , вызовите <xref:System.InvalidCastException> исключение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-137">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="e5efd-138">Одно выражение имеет числовой тип данных, а другой — [Nothing](../nothing.md) .</span><span class="sxs-lookup"><span data-stu-id="e5efd-138">One expression is a numeric data type, and the other is [Nothing](../nothing.md)</span></span>|<span data-ttu-id="e5efd-139">Добавьте со `Nothing` значением 0.</span><span class="sxs-lookup"><span data-stu-id="e5efd-139">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="e5efd-140">Одно выражение — строка, а другая —`Nothing`</span><span class="sxs-lookup"><span data-stu-id="e5efd-140">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="e5efd-141">Объединение со `Nothing` значением "".</span><span class="sxs-lookup"><span data-stu-id="e5efd-141">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="e5efd-142">Если одно выражение является `Object` выражением, Visual Basic выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e5efd-142">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="e5efd-143">Типы данных выражений</span><span class="sxs-lookup"><span data-stu-id="e5efd-143">Data types of expressions</span></span>|<span data-ttu-id="e5efd-144">Действие по компилятору</span><span class="sxs-lookup"><span data-stu-id="e5efd-144">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="e5efd-145">`Object`выражение содержит числовое значение, а другое — числовой тип данных</span><span class="sxs-lookup"><span data-stu-id="e5efd-145">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="e5efd-146">Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="e5efd-146">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e5efd-147">Если `Option Strict` имеет значение `Off` , добавьте.</span><span class="sxs-lookup"><span data-stu-id="e5efd-147">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="e5efd-148">`Object`выражение содержит числовое значение, а другое имеет тип`String`</span><span class="sxs-lookup"><span data-stu-id="e5efd-148">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="e5efd-149">Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="e5efd-149">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e5efd-150">Если `Option Strict` имеет значение `Off` , то неявно преобразует в `String` `Double` и добавьте.</span><span class="sxs-lookup"><span data-stu-id="e5efd-150">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="e5efd-151">Если `String` не удается преобразовать в `Double` , вызовите <xref:System.InvalidCastException> исключение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-151">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="e5efd-152">`Object`выражение содержит строку, а другая — числовой тип данных</span><span class="sxs-lookup"><span data-stu-id="e5efd-152">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="e5efd-153">Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="e5efd-153">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e5efd-154">Если `Option Strict` имеет значение `Off` , то неявно преобразует строку `Object` в `Double` и добавьте.</span><span class="sxs-lookup"><span data-stu-id="e5efd-154">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="e5efd-155">Если строка `Object` не может быть преобразована в `Double` , возникает <xref:System.InvalidCastException> исключение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-155">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="e5efd-156">`Object`выражение содержит строку, а другая — тип`String`</span><span class="sxs-lookup"><span data-stu-id="e5efd-156">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="e5efd-157">Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="e5efd-157">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e5efd-158">Если `Option Strict` имеет значение `Off` , то неявное преобразование `Object` в `String` и сцепление.</span><span class="sxs-lookup"><span data-stu-id="e5efd-158">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="e5efd-159">Если оба выражения являются `Object` выражениями, Visual Basic выполняет следующие действия ( `Option Strict Off` только).</span><span class="sxs-lookup"><span data-stu-id="e5efd-159">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="e5efd-160">Типы данных выражений</span><span class="sxs-lookup"><span data-stu-id="e5efd-160">Data types of expressions</span></span>|<span data-ttu-id="e5efd-161">Действие по компилятору</span><span class="sxs-lookup"><span data-stu-id="e5efd-161">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="e5efd-162">Оба `Object` выражения содержат числовые значения</span><span class="sxs-lookup"><span data-stu-id="e5efd-162">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="e5efd-163">Добавить.</span><span class="sxs-lookup"><span data-stu-id="e5efd-163">Add.</span></span>|  
|<span data-ttu-id="e5efd-164">Оба `Object` выражения имеют тип`String`</span><span class="sxs-lookup"><span data-stu-id="e5efd-164">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="e5efd-165">Объединения.</span><span class="sxs-lookup"><span data-stu-id="e5efd-165">Concatenate.</span></span>|  
|<span data-ttu-id="e5efd-166">Одно `Object` выражение содержит числовое значение, а другое содержит строку.</span><span class="sxs-lookup"><span data-stu-id="e5efd-166">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="e5efd-167">Неявным образом Преобразуйте строку `Object` в `Double` и добавьте.</span><span class="sxs-lookup"><span data-stu-id="e5efd-167">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="e5efd-168">Если строка `Object` не может быть преобразована в числовое значение, то возникает <xref:System.InvalidCastException> исключение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-168">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="e5efd-169">Если любое из `Object` выражений имеет значение [Nothing](../nothing.md) или <xref:System.DBNull> , `+` оператор обрабатывает его как `String` со значением "".</span><span class="sxs-lookup"><span data-stu-id="e5efd-169">If either `Object` expression evaluates to [Nothing](../nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5efd-170">При использовании `+` оператора может быть невозможно определить, будет ли выполняться сложение или объединение строк.</span><span class="sxs-lookup"><span data-stu-id="e5efd-170">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="e5efd-171">Используйте `&` оператор для объединения, чтобы исключить неоднозначность и предоставить код для самостоятельного документирования.</span><span class="sxs-lookup"><span data-stu-id="e5efd-171">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e5efd-172">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="e5efd-172">Overloading</span></span>  
 <span data-ttu-id="e5efd-173">`+`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="e5efd-173">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e5efd-174">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="e5efd-174">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e5efd-175">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e5efd-175">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5efd-176">Пример</span><span class="sxs-lookup"><span data-stu-id="e5efd-176">Example</span></span>  
 <span data-ttu-id="e5efd-177">В следующем примере оператор используется `+` для добавления чисел.</span><span class="sxs-lookup"><span data-stu-id="e5efd-177">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="e5efd-178">Если операнды являются числовыми, Visual Basic вычислит арифметический результат.</span><span class="sxs-lookup"><span data-stu-id="e5efd-178">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="e5efd-179">Арифметический результат представляет сумму двух операндов.</span><span class="sxs-lookup"><span data-stu-id="e5efd-179">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="e5efd-180">Можно также использовать `+` оператор для сцепления строк.</span><span class="sxs-lookup"><span data-stu-id="e5efd-180">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="e5efd-181">Если операнды являются строками, Visual Basic сцепляет их.</span><span class="sxs-lookup"><span data-stu-id="e5efd-181">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="e5efd-182">Результат объединения представляет собой одну строку, состоящую из содержимого двух операндов, один за другим.</span><span class="sxs-lookup"><span data-stu-id="e5efd-182">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="e5efd-183">Если операнды имеют смешанные типы, результат зависит от значения параметра [Option Case](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e5efd-183">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="e5efd-184">В следующем примере показан результат, если `Option Strict` имеет значение `On` .</span><span class="sxs-lookup"><span data-stu-id="e5efd-184">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="e5efd-185">В следующем примере показан результат, если `Option Strict` имеет значение `Off` .</span><span class="sxs-lookup"><span data-stu-id="e5efd-185">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="e5efd-186">Чтобы избежать неоднозначности, следует использовать `&` оператор вместо `+` для объединения.</span><span class="sxs-lookup"><span data-stu-id="e5efd-186">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5efd-187">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e5efd-187">See also</span></span>

- [<span data-ttu-id="e5efd-188">Оператор&</span><span class="sxs-lookup"><span data-stu-id="e5efd-188">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="e5efd-189">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="e5efd-189">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="e5efd-190">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="e5efd-190">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="e5efd-191">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="e5efd-191">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="e5efd-192">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5efd-192">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="e5efd-193">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5efd-193">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="e5efd-194">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="e5efd-194">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
