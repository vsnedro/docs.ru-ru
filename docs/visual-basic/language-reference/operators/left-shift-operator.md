---
title: Оператор <<
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 1128b32a739e7dbf3893dcd19b37247cd4643c85
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370639"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d1614-102">\<\<Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1614-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="d1614-103">Выполняет арифметический сдвиг битового шаблона влево.</span><span class="sxs-lookup"><span data-stu-id="d1614-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1614-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1614-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="d1614-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d1614-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d1614-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d1614-106">Required.</span></span> <span data-ttu-id="d1614-107">Целое числовое значение.</span><span class="sxs-lookup"><span data-stu-id="d1614-107">Integral numeric value.</span></span> <span data-ttu-id="d1614-108">Результат сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="d1614-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="d1614-109">Тип данных такой же, как для `pattern`.</span><span class="sxs-lookup"><span data-stu-id="d1614-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="d1614-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d1614-110">Required.</span></span> <span data-ttu-id="d1614-111">Целое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d1614-111">Integral numeric expression.</span></span> <span data-ttu-id="d1614-112">Битовый шаблон, подлежащий сдвигу.</span><span class="sxs-lookup"><span data-stu-id="d1614-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="d1614-113">Данные должны быть целого типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="d1614-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="d1614-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d1614-114">Required.</span></span> <span data-ttu-id="d1614-115">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d1614-115">Numeric expression.</span></span> <span data-ttu-id="d1614-116">Количество разрядов, на которое следует сдвинуть битовый шаблон.</span><span class="sxs-lookup"><span data-stu-id="d1614-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="d1614-117">Данные должны относиться к типу `Integer` или допускать расширение до типа `Integer`.</span><span class="sxs-lookup"><span data-stu-id="d1614-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1614-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d1614-118">Remarks</span></span>  
 <span data-ttu-id="d1614-119">Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец.</span><span class="sxs-lookup"><span data-stu-id="d1614-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="d1614-120">При выполнении арифметического сдвига влево биты, сдвинутые за пределы диапазона результирующего типа данных, отбрасываются, а позиции битов, освобожденные справа, устанавливаются в ноль.</span><span class="sxs-lookup"><span data-stu-id="d1614-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="d1614-121">Чтобы предотвратить сдвиг на больше бит, чем может вместить результат, Visual Basic маскирует значение `amount` с маской размера, соответствующей типу данных `pattern` .</span><span class="sxs-lookup"><span data-stu-id="d1614-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="d1614-122">Двоичные значения и этих значений используются для величины сдвига.</span><span class="sxs-lookup"><span data-stu-id="d1614-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="d1614-123">Ниже приведены маски размера.</span><span class="sxs-lookup"><span data-stu-id="d1614-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="d1614-124">Тип данных`pattern`</span><span class="sxs-lookup"><span data-stu-id="d1614-124">Data type of `pattern`</span></span>|<span data-ttu-id="d1614-125">Маска размера (десятичная)</span><span class="sxs-lookup"><span data-stu-id="d1614-125">Size mask (decimal)</span></span>|<span data-ttu-id="d1614-126">Маска размера (шестнадцатеричная)</span><span class="sxs-lookup"><span data-stu-id="d1614-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="d1614-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="d1614-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="d1614-128">7</span><span class="sxs-lookup"><span data-stu-id="d1614-128">7</span></span>|<span data-ttu-id="d1614-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="d1614-129">&H00000007</span></span>|  
|<span data-ttu-id="d1614-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="d1614-130">`Short`, `UShort`</span></span>|<span data-ttu-id="d1614-131">15</span><span class="sxs-lookup"><span data-stu-id="d1614-131">15</span></span>|<span data-ttu-id="d1614-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="d1614-132">&H0000000F</span></span>|  
|<span data-ttu-id="d1614-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="d1614-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="d1614-134">31</span><span class="sxs-lookup"><span data-stu-id="d1614-134">31</span></span>|<span data-ttu-id="d1614-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="d1614-135">&H0000001F</span></span>|  
|<span data-ttu-id="d1614-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="d1614-136">`Long`, `ULong`</span></span>|<span data-ttu-id="d1614-137">63</span><span class="sxs-lookup"><span data-stu-id="d1614-137">63</span></span>|<span data-ttu-id="d1614-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="d1614-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="d1614-139">Если `amount` равен нулю, значение `result` идентично значению `pattern` .</span><span class="sxs-lookup"><span data-stu-id="d1614-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="d1614-140">Если `amount` имеет отрицательное значение, оно принимается в качестве значения без знака и маскируется с соответствующей маской размера.</span><span class="sxs-lookup"><span data-stu-id="d1614-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="d1614-141">Арифметические сдвиги никогда не создают исключений переполнения.</span><span class="sxs-lookup"><span data-stu-id="d1614-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1614-142">`<<`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d1614-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d1614-143">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="d1614-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="d1614-144">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d1614-144">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1614-145">Пример</span><span class="sxs-lookup"><span data-stu-id="d1614-145">Example</span></span>  
 <span data-ttu-id="d1614-146">В следующем примере оператор используется `<<` для выполнения арифметических сдвигов влево по целочисленным значениям.</span><span class="sxs-lookup"><span data-stu-id="d1614-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="d1614-147">Результат всегда имеет тот же тип данных, что и выражение, для которого выполняется сдвиг.</span><span class="sxs-lookup"><span data-stu-id="d1614-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="d1614-148">Результаты предыдущего примера выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d1614-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="d1614-149">`result1`— 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="d1614-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="d1614-150">`result2`— 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="d1614-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="d1614-151">`result3`— 32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="d1614-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="d1614-152">`result4`— 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="d1614-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="d1614-153">`result5`равно 0 (смещено 15 позиций влево).</span><span class="sxs-lookup"><span data-stu-id="d1614-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="d1614-154">Сумма сдвига для `result4` вычисляется как 17 и 15, что равно 1.</span><span class="sxs-lookup"><span data-stu-id="d1614-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1614-155">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d1614-155">See also</span></span>

- [<span data-ttu-id="d1614-156">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="d1614-156">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="d1614-157">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="d1614-157">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="d1614-158">Оператор<<=</span><span class="sxs-lookup"><span data-stu-id="d1614-158"><<= Operator</span></span>](left-shift-assignment-operator.md)
- [<span data-ttu-id="d1614-159">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1614-159">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="d1614-160">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="d1614-160">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="d1614-161">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1614-161">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
