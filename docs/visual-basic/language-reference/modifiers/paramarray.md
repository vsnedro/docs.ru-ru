---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: e3c24818ea87884a0dd9b42c604e13e16ca6d3d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391824"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="ecc55-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecc55-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="ecc55-103">Указывает, что параметр процедуры принимает необязательный массив элементов указанного типа.</span><span class="sxs-lookup"><span data-stu-id="ecc55-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="ecc55-104">`ParamArray`может использоваться только в последнем параметре списка параметров.</span><span class="sxs-lookup"><span data-stu-id="ecc55-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc55-105">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ecc55-105">Remarks</span></span>  
 <span data-ttu-id="ecc55-106">`ParamArray`позволяет передавать процедуре произвольное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="ecc55-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="ecc55-107">`ParamArray`Параметр всегда объявляется с помощью [ByVal](byval.md).</span><span class="sxs-lookup"><span data-stu-id="ecc55-107">A `ParamArray` parameter is always declared using [ByVal](byval.md).</span></span>  
  
 <span data-ttu-id="ecc55-108">Можно указать один или несколько аргументов для параметра, `ParamArray` передав массив соответствующего типа данных, список значений с разделителями-запятыми или ничего вообще.</span><span class="sxs-lookup"><span data-stu-id="ecc55-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="ecc55-109">Дополнительные сведения см. в разделе «вызов ParamArray» в [массивах параметров](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="ecc55-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ecc55-110">Всякий раз при работе с массивом, который может быть неограниченным большим, существует риск перегрузки внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="ecc55-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="ecc55-111">Если вы принимаете массив параметров из вызывающего кода, следует проверить его длину и предпринять соответствующие шаги, если оно слишком велико для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="ecc55-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="ecc55-112">Модификатор `ParamArray` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="ecc55-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ecc55-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="ecc55-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="ecc55-114">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="ecc55-114">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="ecc55-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="ecc55-115">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="ecc55-116">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="ecc55-116">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ecc55-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ecc55-117">See also</span></span>

- [<span data-ttu-id="ecc55-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ecc55-118">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="ecc55-119">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="ecc55-119">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
