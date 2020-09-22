---
title: '* Оператор'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 7038fef4258d190b726a851b26f2a2840ff3c0ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873362"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="56f9a-102">Оператор \* (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56f9a-102">\* Operator (Visual Basic)</span></span>

<span data-ttu-id="56f9a-103">Перемножает два числа.</span><span class="sxs-lookup"><span data-stu-id="56f9a-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56f9a-104">Syntax</span></span>  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="56f9a-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="56f9a-105">Parts</span></span>  
  
|<span data-ttu-id="56f9a-106">Термин</span><span class="sxs-lookup"><span data-stu-id="56f9a-106">Term</span></span>|<span data-ttu-id="56f9a-107">Определение</span><span class="sxs-lookup"><span data-stu-id="56f9a-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="56f9a-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="56f9a-108">Required.</span></span> <span data-ttu-id="56f9a-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="56f9a-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="56f9a-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="56f9a-110">Required.</span></span> <span data-ttu-id="56f9a-111">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="56f9a-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="56f9a-112">Результат</span><span class="sxs-lookup"><span data-stu-id="56f9a-112">Result</span></span>  

 <span data-ttu-id="56f9a-113">Результатом является произведение `number1` и `number2` .</span><span class="sxs-lookup"><span data-stu-id="56f9a-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="56f9a-114">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="56f9a-114">Supported Types</span></span>  

 <span data-ttu-id="56f9a-115">Все числовые типы, включая неподписанные и типы с плавающей запятой, и `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="56f9a-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56f9a-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="56f9a-116">Remarks</span></span>  

 <span data-ttu-id="56f9a-117">Тип данных результата зависит от типов операндов.</span><span class="sxs-lookup"><span data-stu-id="56f9a-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="56f9a-118">В следующей таблице показано, как определяется тип данных результата.</span><span class="sxs-lookup"><span data-stu-id="56f9a-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="56f9a-119">Типы данных операндов</span><span class="sxs-lookup"><span data-stu-id="56f9a-119">Operand data types</span></span>|<span data-ttu-id="56f9a-120">Тип данных результата</span><span class="sxs-lookup"><span data-stu-id="56f9a-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="56f9a-121">Оба выражения являются целочисленными типами данных ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ulong](../data-types/ulong-data-type.md)).</span><span class="sxs-lookup"><span data-stu-id="56f9a-121">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="56f9a-122">Числовой тип данных, подходящий для типов данных `number1` и `number2` .</span><span class="sxs-lookup"><span data-stu-id="56f9a-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="56f9a-123">См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="56f9a-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="56f9a-124">Оба выражения являются [десятичными](../data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="56f9a-124">Both expressions are [Decimal](../data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="56f9a-125">Оба выражения являются [одиночными](../data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="56f9a-125">Both expressions are [Single](../data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="56f9a-126">Одно из выражений является типом данных с плавающей запятой ( `Single` или [Double](../data-types/double-data-type.md)), но не оба `Single` (Обратите внимание `Decimal` , что это не тип данных с плавающей запятой).</span><span class="sxs-lookup"><span data-stu-id="56f9a-126">Either expression is a floating-point data type (`Single` or [Double](../data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="56f9a-127">Если выражение принимает значение [Nothing](../nothing.md), оно считается нулевым.</span><span class="sxs-lookup"><span data-stu-id="56f9a-127">If an expression evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="56f9a-128">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="56f9a-128">Overloading</span></span>  

 <span data-ttu-id="56f9a-129">`*`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="56f9a-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="56f9a-130">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="56f9a-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="56f9a-131">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="56f9a-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56f9a-132">Пример</span><span class="sxs-lookup"><span data-stu-id="56f9a-132">Example</span></span>  

 <span data-ttu-id="56f9a-133">В этом примере `*` оператор используется для умножения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="56f9a-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="56f9a-134">Результатом является произведение двух операндов.</span><span class="sxs-lookup"><span data-stu-id="56f9a-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="56f9a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="56f9a-135">See also</span></span>

- [<span data-ttu-id="56f9a-136">Оператор \* =</span><span class="sxs-lookup"><span data-stu-id="56f9a-136">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="56f9a-137">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="56f9a-137">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="56f9a-138">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56f9a-138">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="56f9a-139">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="56f9a-139">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="56f9a-140">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56f9a-140">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
