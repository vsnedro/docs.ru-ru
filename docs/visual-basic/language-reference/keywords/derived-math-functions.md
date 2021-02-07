---
description: 'Дополнительные сведения: Производные математические функции (Visual Basic)'
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
ms.openlocfilehash: daaed1312f08cecc0c68af0e36d574424fc526a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730776"
---
# <a name="derived-math-functions-visual-basic"></a>Производные математические функции (Visual Basic)

В следующей таблице показаны невстроенные математические функции, которые могут быть производными от встроенных математических функций <xref:System.Math?displayProperty=nameWithType> объекта. Доступ к встроенным математическим функциям можно получить, добавив `Imports System.Math` в файл или проект.  
  
|Компонент|Производные эквиваленты|  
|--------------|-------------------------|  
|Секанс (с (x))|1/cos (x)|  
|Косеканс (CSC (x))|1/Sin (x)|  
|Котангенс (Ктан (x))|1/Tan (x)|  
|Обратный Синус (ASIN (x))|ATAN (x/Sqrt (-x * x + 1))|  
|Обратный косинус (ACOS (x))|ATAN (-x/Sqrt (-x * x + 1)) + 2 \* ATAN (1)|  
|Обратный секанс (АСЕК (x))|2 * ATAN (1) — ATAN (Sign (x)/SQRT (x \* x – 1))|  
|Обратный косеканс (ACSC (x))|ATAN (Sign (x)/SQRT (x * x – 1))|  
|Обратная котангенс (Акот (x))|2 * ATAN (1) — ATAN (x)|  
|Гиперболический синус (SINH (x))|(Exp (x) – EXP (-x))/2|  
|Гиперболический косинус (COSH (x))|(Exp (x) + EXP (-x))/2|  
|Гиперболический тангенс (TANH (x))|(Exp (x) – EXP (-x))/(exp (x) + EXP (-x))|  
|Гиперболический секанс (Сеч (x))|2/(exp (x) + EXP (-x))|  
|Гиперболический косеканс (Ксч (x))|2/(exp (x) — EXP (-x))|  
|Гиперболический котангенс (КОС (x))|(Exp (x) + EXP (-x))/(exp (x) – EXP (-x))|  
|Обратный гиперболический синус (Asinh (x))|Log (x + Sqrt (x * x + 1))|  
|Обратный гиперболический косинус (ACOSH (x))|Log (x + Sqrt (x * x – 1))|  
|Обратный гиперболический тангенс (ATANH (x))|Журнал ((1 + x)/(1 – x))/2|  
|Обратный гиперболический секанс (Асеч (x))|Log ((sqrt (-x * x + 1) + 1)/x)|  
|Обратный гиперболический косеканс (Аксч (x))|Log ((знак (x) * SQRT (x \* x + 1) + 1)/x)|  
|Обратный гиперболический котангенс (Акос (x))|Log ((x + 1)/(x – 1))/2|  
  
## <a name="see-also"></a>См. также

- [Математические функции](../functions/math-functions.md)
