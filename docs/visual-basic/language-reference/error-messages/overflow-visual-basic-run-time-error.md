---
title: Переполнение (Ошибка во время выполнения Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: e287d6c24eca75d8bf20181a201056f467d6fc4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871218"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="46829-102">Переполнение (Ошибка во время выполнения Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46829-102">Overflow (Visual Basic Run-Time Error)</span></span>

<span data-ttu-id="46829-103">При попыток присваивания, превышающего ограничения целевого объекта назначения, возникает переполнение.</span><span class="sxs-lookup"><span data-stu-id="46829-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46829-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="46829-104">To correct this error</span></span>  
  
1. <span data-ttu-id="46829-105">Убедитесь, что результаты присваивания, вычисления и преобразования типов данных не слишком велики для представления в диапазоне переменных, допустимых для этого типа значений, и присвойте значение переменной типа, которая может содержать больший диапазон значений (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="46829-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="46829-106">Убедитесь, что назначения свойств соответствуют диапазону свойства, в котором они были сделаны.</span><span class="sxs-lookup"><span data-stu-id="46829-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="46829-107">Убедитесь, что числа, используемые в вычислениях, приведенных к целому числу, не имеют результатов, превышающих целые числа.</span><span class="sxs-lookup"><span data-stu-id="46829-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46829-108">См. также</span><span class="sxs-lookup"><span data-stu-id="46829-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="46829-109">Типы данных</span><span class="sxs-lookup"><span data-stu-id="46829-109">Data Types</span></span>](../data-types/index.md)
- [<span data-ttu-id="46829-110">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="46829-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
