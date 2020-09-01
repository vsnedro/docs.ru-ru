---
description: Справочник по C#. Checked и Unchecked
title: Справочник по C#. Checked и Unchecked
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: a8d6a26e28062da682689bf64a9e38ea5fd158b2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138271"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="1598c-103">Checked и Unchecked (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1598c-103">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="1598c-104">Строка кода C# может выполняться как в проверенном, так и в непроверенном контексте.</span><span class="sxs-lookup"><span data-stu-id="1598c-104">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="1598c-105">В проверенном контексте арифметическое переполнение создает исключение.</span><span class="sxs-lookup"><span data-stu-id="1598c-105">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="1598c-106">В непроверяемом контексте арифметическое переполнение игнорируется и результат усекается путем удаления старших разрядов, которые не помещаются в целевой тип данных.</span><span class="sxs-lookup"><span data-stu-id="1598c-106">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="1598c-107">[checked](checked.md). Укажите проверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="1598c-107">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="1598c-108">[unchecked](unchecked.md). Укажите непроверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="1598c-108">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="1598c-109">Следующие операции не затрагиваются проверкой переполнения.</span><span class="sxs-lookup"><span data-stu-id="1598c-109">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="1598c-110">Выражения, использующие следующие предопределенные операторы на целочисленных типах:</span><span class="sxs-lookup"><span data-stu-id="1598c-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="1598c-111">`++`, `--`; унарные `-`, `+`, `-`, `*`, `/`.</span><span class="sxs-lookup"><span data-stu-id="1598c-111">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="1598c-112">Явные числовые преобразования между целочисленными типами либо из `float` или `double` в целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="1598c-112">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="1598c-113">Если ни `checked`, ни `unchecked` не указаны, контекст по умолчанию для неконстантных выражений (выражения, вычисляемые во время выполнения) определяется по значению параметра компилятора [-checked](../compiler-options/checked-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1598c-113">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="1598c-114">По умолчанию значение этого параметра не задано, и арифметические операции выполняются в непроверенном контексте.</span><span class="sxs-lookup"><span data-stu-id="1598c-114">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>

 <span data-ttu-id="1598c-115">Для константных выражений (выражения, которые можно полностью вычислить во время компиляции) контекстом по умолчанию является проверяемый.</span><span class="sxs-lookup"><span data-stu-id="1598c-115">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="1598c-116">Если только константное выражение явным образом не размещено в непроверенном контексте, переполнения, возникающие при вычислении выражения во время компиляции, вызывают ошибки времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="1598c-116">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1598c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1598c-117">See also</span></span>

- [<span data-ttu-id="1598c-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1598c-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1598c-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1598c-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1598c-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="1598c-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1598c-121">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="1598c-121">Statement Keywords</span></span>](statement-keywords.md)
