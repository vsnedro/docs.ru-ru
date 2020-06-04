---
title: Переполнение (Ошибка во время выполнения Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 5606ae8188c12142800adef46819791b732ff73c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387274"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="4dbcd-102">Переполнение (Ошибка во время выполнения Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dbcd-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="4dbcd-103">При попыток присваивания, превышающего ограничения целевого объекта назначения, возникает переполнение.</span><span class="sxs-lookup"><span data-stu-id="4dbcd-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4dbcd-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4dbcd-104">To correct this error</span></span>  
  
1. <span data-ttu-id="4dbcd-105">Убедитесь, что результаты присваивания, вычисления и преобразования типов данных не слишком велики для представления в диапазоне переменных, допустимых для этого типа значений, и присвойте значение переменной типа, которая может содержать больший диапазон значений (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="4dbcd-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="4dbcd-106">Убедитесь, что назначения свойств соответствуют диапазону свойства, в котором они были сделаны.</span><span class="sxs-lookup"><span data-stu-id="4dbcd-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="4dbcd-107">Убедитесь, что числа, используемые в вычислениях, приведенных к целому числу, не имеют результатов, превышающих целые числа.</span><span class="sxs-lookup"><span data-stu-id="4dbcd-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dbcd-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4dbcd-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="4dbcd-109">Типы данных</span><span class="sxs-lookup"><span data-stu-id="4dbcd-109">Data Types</span></span>](../data-types/index.md)
- [<span data-ttu-id="4dbcd-110">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="4dbcd-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
