---
title: Практическое руководство. Преобразование объекта в другой тип
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: b89e996324d9ec22fc243b59502f3d36fefdee60
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090226"
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
  
## <a name="see-also"></a>См. также

- <xref:System.Object>
- [Преобразование типов в Visual Basic](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](implicit-and-explicit-conversions.md)
- [Преобразования значений между строковыми и другими типами](conversions-between-strings-and-other-types.md)
- [Преобразования массивов](array-conversions.md)
- [Структуры](structures.md)
- [Типы данных](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
