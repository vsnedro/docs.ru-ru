---
title: Производные математические функции
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 611f3d8faf2148b8a983467d9ace4fd6c18b30e6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373898"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="2edc2-102">Производные математические функции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2edc2-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="2edc2-103">В следующей таблице показаны невстроенные математические функции, которые могут быть производными от встроенных математических функций <xref:System.Math?displayProperty=nameWithType> объекта.</span><span class="sxs-lookup"><span data-stu-id="2edc2-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="2edc2-104">Доступ к встроенным математическим функциям можно получить, добавив `Imports System.Math` в файл или проект.</span><span class="sxs-lookup"><span data-stu-id="2edc2-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="2edc2-105">Функция</span><span class="sxs-lookup"><span data-stu-id="2edc2-105">Function</span></span>|<span data-ttu-id="2edc2-106">Производные эквиваленты</span><span class="sxs-lookup"><span data-stu-id="2edc2-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="2edc2-107">Секанс (с (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-107">Secant (Sec(x))</span></span>|<span data-ttu-id="2edc2-108">1/cos (x)</span><span class="sxs-lookup"><span data-stu-id="2edc2-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="2edc2-109">Косеканс (CSC (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="2edc2-110">1/Sin (x)</span><span class="sxs-lookup"><span data-stu-id="2edc2-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="2edc2-111">Котангенс (Ктан (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="2edc2-112">1/Tan (x)</span><span class="sxs-lookup"><span data-stu-id="2edc2-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="2edc2-113">Обратный Синус (ASIN (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="2edc2-114">ATAN (x/Sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="2edc2-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="2edc2-115">Обратный косинус (ACOS (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="2edc2-116">ATAN (-x/Sqrt (-x \* x + 1)) + 2 \* ATAN (1)</span><span class="sxs-lookup"><span data-stu-id="2edc2-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="2edc2-117">Обратный секанс (АСЕК (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="2edc2-118">2 \* ATAN (1) — ATAN (Sign (x)/SQRT (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="2edc2-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="2edc2-119">Обратный косеканс (ACSC (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="2edc2-120">ATAN (Sign (x)/SQRT (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="2edc2-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="2edc2-121">Обратная котангенс (Акот (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="2edc2-122">2 \* ATAN (1) — ATAN (x)</span><span class="sxs-lookup"><span data-stu-id="2edc2-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="2edc2-123">Гиперболический синус (SINH (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="2edc2-124">(Exp (x) – EXP (-x))/2</span><span class="sxs-lookup"><span data-stu-id="2edc2-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="2edc2-125">Гиперболический косинус (COSH (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="2edc2-126">(Exp (x) + EXP (-x))/2</span><span class="sxs-lookup"><span data-stu-id="2edc2-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="2edc2-127">Гиперболический тангенс (TANH (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="2edc2-128">(Exp (x) – EXP (-x))/(exp (x) + EXP (-x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="2edc2-129">Гиперболический секанс (Сеч (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="2edc2-130">2/(exp (x) + EXP (-x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="2edc2-131">Гиперболический косеканс (Ксч (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="2edc2-132">2/(exp (x) — EXP (-x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="2edc2-133">Гиперболический котангенс (КОС (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="2edc2-134">(Exp (x) + EXP (-x))/(exp (x) – EXP (-x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="2edc2-135">Обратный гиперболический синус (Asinh (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="2edc2-136">Log (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="2edc2-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="2edc2-137">Обратный гиперболический косинус (ACOSH (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="2edc2-138">Log (x + Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="2edc2-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="2edc2-139">Обратный гиперболический тангенс (ATANH (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="2edc2-140">Журнал ((1 + x)/(1 – x))/2</span><span class="sxs-lookup"><span data-stu-id="2edc2-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="2edc2-141">Обратный гиперболический секанс (Асеч (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="2edc2-142">Log ((sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="2edc2-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="2edc2-143">Обратный гиперболический косеканс (Аксч (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="2edc2-144">Log ((знак (x) \* SQRT (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="2edc2-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="2edc2-145">Обратный гиперболический котангенс (Акос (x))</span><span class="sxs-lookup"><span data-stu-id="2edc2-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="2edc2-146">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="2edc2-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2edc2-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2edc2-147">See also</span></span>

- [<span data-ttu-id="2edc2-148">Математические функции</span><span class="sxs-lookup"><span data-stu-id="2edc2-148">Math Functions</span></span>](../functions/math-functions.md)
