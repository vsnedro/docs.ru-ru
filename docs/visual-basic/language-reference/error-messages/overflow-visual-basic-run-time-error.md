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
# <a name="overflow-visual-basic-run-time-error"></a>Переполнение (Ошибка во время выполнения Visual Basic)
При попыток присваивания, превышающего ограничения целевого объекта назначения, возникает переполнение.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что результаты присваивания, вычисления и преобразования типов данных не слишком велики для представления в диапазоне переменных, допустимых для этого типа значений, и присвойте значение переменной типа, которая может содержать больший диапазон значений (при необходимости).  
  
2. Убедитесь, что назначения свойств соответствуют диапазону свойства, в котором они были сделаны.  
  
3. Убедитесь, что числа, используемые в вычислениях, приведенных к целому числу, не имеют результатов, превышающих целые числа.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Типы данных](../data-types/index.md)
- [Типы ошибок](../../programming-guide/language-features/error-types.md)
