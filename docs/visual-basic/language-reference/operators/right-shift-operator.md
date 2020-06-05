---
title: '>> Оператор'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 10b07da22b8b43d6a966fa7c334ac6a0ef4b430d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406376"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f11d0-102">Оператор >> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f11d0-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="f11d0-103">Выполняет арифметический сдвиг битового шаблона вправо.</span><span class="sxs-lookup"><span data-stu-id="f11d0-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f11d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f11d0-104">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="f11d0-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="f11d0-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f11d0-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f11d0-106">Required.</span></span> <span data-ttu-id="f11d0-107">Целое числовое значение.</span><span class="sxs-lookup"><span data-stu-id="f11d0-107">Integral numeric value.</span></span> <span data-ttu-id="f11d0-108">Результат сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="f11d0-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="f11d0-109">Тип данных такой же, как для `pattern`.</span><span class="sxs-lookup"><span data-stu-id="f11d0-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="f11d0-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f11d0-110">Required.</span></span> <span data-ttu-id="f11d0-111">Целое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f11d0-111">Integral numeric expression.</span></span> <span data-ttu-id="f11d0-112">Битовый шаблон, подлежащий сдвигу.</span><span class="sxs-lookup"><span data-stu-id="f11d0-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="f11d0-113">Данные должны быть целого типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="f11d0-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="f11d0-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f11d0-114">Required.</span></span> <span data-ttu-id="f11d0-115">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f11d0-115">Numeric expression.</span></span> <span data-ttu-id="f11d0-116">Количество разрядов, на которое следует сдвинуть битовый шаблон.</span><span class="sxs-lookup"><span data-stu-id="f11d0-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="f11d0-117">Данные должны относиться к типу `Integer` или допускать расширение до типа `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f11d0-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f11d0-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f11d0-118">Remarks</span></span>  
 <span data-ttu-id="f11d0-119">Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец.</span><span class="sxs-lookup"><span data-stu-id="f11d0-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="f11d0-120">При арифметическом сдвиге вправо биты, сдвинутые за пределы крайней правой позиции, отбрасываются, а самый левый бит (знак) распространяется на биты, освобожденные слева.</span><span class="sxs-lookup"><span data-stu-id="f11d0-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="f11d0-121">Это означает, что если `pattern` имеет отрицательное значение, освобождаемые позиции задаются как один; в противном случае — значение 0.</span><span class="sxs-lookup"><span data-stu-id="f11d0-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="f11d0-122">Обратите внимание, что типы данных `Byte` ,, `UShort` и не `UInteger` `ULong` подписаны, поэтому для распространения нет бита знака.</span><span class="sxs-lookup"><span data-stu-id="f11d0-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="f11d0-123">Если `pattern` имеет любой тип без знака, освобождаемые позиции всегда устанавливаются в ноль.</span><span class="sxs-lookup"><span data-stu-id="f11d0-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="f11d0-124">Чтобы предотвратить сдвиг на большее количество битов, чем может вместить результат, Visual Basic маскирует значение `amount` с маской размера, соответствующей типу данных `pattern` .</span><span class="sxs-lookup"><span data-stu-id="f11d0-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="f11d0-125">Двоичные значения и этих значений используются для величины сдвига.</span><span class="sxs-lookup"><span data-stu-id="f11d0-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="f11d0-126">Ниже приведены маски размера.</span><span class="sxs-lookup"><span data-stu-id="f11d0-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="f11d0-127">Тип данных`pattern`</span><span class="sxs-lookup"><span data-stu-id="f11d0-127">Data type of `pattern`</span></span>|<span data-ttu-id="f11d0-128">Маска размера (десятичная)</span><span class="sxs-lookup"><span data-stu-id="f11d0-128">Size mask (decimal)</span></span>|<span data-ttu-id="f11d0-129">Маска размера (шестнадцатеричная)</span><span class="sxs-lookup"><span data-stu-id="f11d0-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="f11d0-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="f11d0-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="f11d0-131">7</span><span class="sxs-lookup"><span data-stu-id="f11d0-131">7</span></span>|<span data-ttu-id="f11d0-132">&H00000007</span><span class="sxs-lookup"><span data-stu-id="f11d0-132">&H00000007</span></span>|  
|<span data-ttu-id="f11d0-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="f11d0-133">`Short`, `UShort`</span></span>|<span data-ttu-id="f11d0-134">15</span><span class="sxs-lookup"><span data-stu-id="f11d0-134">15</span></span>|<span data-ttu-id="f11d0-135">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="f11d0-135">&H0000000F</span></span>|  
|<span data-ttu-id="f11d0-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="f11d0-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="f11d0-137">31</span><span class="sxs-lookup"><span data-stu-id="f11d0-137">31</span></span>|<span data-ttu-id="f11d0-138">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="f11d0-138">&H0000001F</span></span>|  
|<span data-ttu-id="f11d0-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="f11d0-139">`Long`, `ULong`</span></span>|<span data-ttu-id="f11d0-140">63</span><span class="sxs-lookup"><span data-stu-id="f11d0-140">63</span></span>|<span data-ttu-id="f11d0-141">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="f11d0-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="f11d0-142">Если `amount` равен нулю, значение `result` идентично значению `pattern` .</span><span class="sxs-lookup"><span data-stu-id="f11d0-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="f11d0-143">Если `amount` имеет отрицательное значение, оно принимается в качестве значения без знака и маскируется с соответствующей маской размера.</span><span class="sxs-lookup"><span data-stu-id="f11d0-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="f11d0-144">Арифметические сдвиги никогда не создают исключений переполнения.</span><span class="sxs-lookup"><span data-stu-id="f11d0-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f11d0-145">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="f11d0-145">Overloading</span></span>  
 <span data-ttu-id="f11d0-146">`>>`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="f11d0-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f11d0-147">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="f11d0-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f11d0-148">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f11d0-148">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f11d0-149">Пример</span><span class="sxs-lookup"><span data-stu-id="f11d0-149">Example</span></span>  
 <span data-ttu-id="f11d0-150">В следующем примере оператор используется `>>` для выполнения арифметических сдвигов в целочисленных значениях вправо.</span><span class="sxs-lookup"><span data-stu-id="f11d0-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="f11d0-151">Результат всегда имеет тот же тип данных, что и выражение, для которого выполняется сдвиг.</span><span class="sxs-lookup"><span data-stu-id="f11d0-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="f11d0-152">Ниже приведены результаты предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="f11d0-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="f11d0-153">`result1`— 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="f11d0-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="f11d0-154">`result2`— 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="f11d0-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="f11d0-155">`result3`равно 2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="f11d0-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="f11d0-156">`result4`— 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="f11d0-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="f11d0-157">`result5`равно 0 (смещено 15 позиций вправо).</span><span class="sxs-lookup"><span data-stu-id="f11d0-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="f11d0-158">Сумма сдвига для вычисляется `result4` как 18 и 15, что равно 2.</span><span class="sxs-lookup"><span data-stu-id="f11d0-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="f11d0-159">В следующем примере показаны арифметические сдвиги для отрицательного значения.</span><span class="sxs-lookup"><span data-stu-id="f11d0-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="f11d0-160">Ниже приведены результаты предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="f11d0-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="f11d0-161">`negresult1`— 512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="f11d0-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="f11d0-162">`negresult2`равно-1 (бит подписи распространяется);</span><span class="sxs-lookup"><span data-stu-id="f11d0-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f11d0-163">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f11d0-163">See also</span></span>

- [<span data-ttu-id="f11d0-164">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="f11d0-164">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="f11d0-165">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="f11d0-165">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="f11d0-166">Оператор>>=</span><span class="sxs-lookup"><span data-stu-id="f11d0-166">>>= Operator</span></span>](right-shift-assignment-operator.md)
- [<span data-ttu-id="f11d0-167">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f11d0-167">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="f11d0-168">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="f11d0-168">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="f11d0-169">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f11d0-169">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
