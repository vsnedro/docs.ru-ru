---
description: 'Дополнительные сведения: переполнение (ошибка Visual Basic Run-Time)'
title: Переполнение (Ошибка во время выполнения Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: a01a8916e09f9278dbdf6d594c5ef84d63b04c51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795460"
---
# <a name="overflow-visual-basic-run-time-error"></a>Переполнение (Ошибка во время выполнения Visual Basic)

При попыток присваивания, превышающего ограничения целевого объекта назначения, возникает переполнение.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что результаты присваивания, вычисления и преобразования типов данных не слишком велики для представления в диапазоне переменных, допустимых для этого типа значений, и присвойте значение переменной типа, которая может содержать больший диапазон значений (при необходимости).  
  
2. Убедитесь, что назначения свойств соответствуют диапазону свойства, в котором они были сделаны.  
  
3. Убедитесь, что числа, используемые в вычислениях, приведенных к целому числу, не имеют результатов, превышающих целые числа.  
  
## <a name="see-also"></a>См. также

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Типы данных](../data-types/index.md)
- [Типы ошибок](../../programming-guide/language-features/error-types.md)
