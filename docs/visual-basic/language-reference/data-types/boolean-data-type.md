---
title: Логический тип данных
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 851c524a83c5f24b77a151634a96798249c5905e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374425"
---
# <a name="boolean-data-type-visual-basic"></a>Тип данных Boolean (Visual Basic)

Содержит значения, которые могут быть только `True` или `False` . Ключевые слова `True` и `False` соответствуют двум состояниям `Boolean` переменных.  
  
## <a name="remarks"></a>Комментарии  

 Используйте [логический тип данных (Visual Basic)](boolean-data-type.md) для хранения двух значений, таких как true/false, да/нет или ON/OFF.  
  
 Значением свойства `Boolean` по умолчанию является `False`.  
  
 `Boolean`значения не хранятся в виде чисел, а хранимые значения не должны быть эквивалентны числам. Никогда не следует писать код, основанный на эквивалентных числовых значениях для `True` и `False` . Везде, где это возможно, следует ограничить использование `Boolean` переменных логическими значениями, для которых они предназначены.  
  
## <a name="type-conversions"></a>Преобразования типов  

 Когда Visual Basic преобразует числовые значения типа данных в значение `Boolean` , значение 0 становится равным, `False` а все остальные значения становятся `True` . Когда Visual Basic преобразует `Boolean` значения в числовые типы, преобразуется в `False` 0 и `True` преобразуется в значение-1.  
  
 При преобразовании между `Boolean` значениями и числовыми типами данных следует помнить, что методы преобразования .NET Framework не всегда дают те же результаты, что и ключевые слова Visual Basicного преобразования. Это обусловлено тем, что Visual Basicное преобразование поддерживает поведение, совместимое с предыдущими версиями. Дополнительные сведения см. в разделе "неверное Преобразование логического типа в числовой тип" раздела [Устранение неполадок типов данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
- **Отрицательные числа.** `Boolean`не является числовым типом и не может представлять отрицательное значение. В любом случае не следует использовать `Boolean` для хранения числовых значений.  
  
- **Символы типа.** `Boolean`не имеет символа типа литерала или символа типа идентификатора.  
  
- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  

 В следующем примере `runningVB` — это `Boolean` переменная, в которой хранится простой параметр Да/нет.  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Boolean?displayProperty=nameWithType>
- [Типы данных](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType Function](../functions/ctype-function.md)
