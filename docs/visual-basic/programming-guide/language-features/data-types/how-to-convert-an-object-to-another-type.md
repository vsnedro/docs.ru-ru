---
description: Дополнительные сведения см. в статье как преобразовать объект в другой тип в Visual Basic
title: Практическое руководство. Преобразование объекта в другой тип
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: d6840cfd440483720f8ca9a0fa0140c3727a8688
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100484032"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Практическое руководство. Преобразование объекта к другому типу в Visual Basic

Преобразование `Object` переменной в другой тип данных осуществляется с помощью ключевого слова преобразования, например [CType Function](../../../language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Пример  

 В следующем примере переменная преобразуется `Object` в `Integer` и `String` .  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Если известно, что содержимое `Object` переменной относится к определенному типу данных, лучше преобразовать переменную в этот тип данных. Если вы продолжаете использовать `Object` переменную, вы используете *упаковку* и *распаковку* (для типа значения) или *позднее связывание* (для ссылочного типа). Все эти операции занимают некоторое время и снижают производительность.  
  
## <a name="compile-the-code"></a>Компиляция кода  

 Для этого примера требуются:  
  
- ссылка на пространство имен <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Object>
- [Преобразование типов в Visual Basic](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](implicit-and-explicit-conversions.md)
- [Преобразования значений между строковыми и другими типами](conversions-between-strings-and-other-types.md)
- [Преобразования массивов](array-conversions.md)
- [Структуры](structures.md)
- [Типы данных](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
