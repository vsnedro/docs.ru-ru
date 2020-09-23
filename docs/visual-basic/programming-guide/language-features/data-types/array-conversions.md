---
title: Преобразования массивов
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 375c75c954f3be535272d674d9b786cad46b1a01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077193"
---
# <a name="array-conversions-visual-basic"></a>Преобразование массивов (Visual Basic)

Тип массива можно преобразовать в другой тип массива при условии соблюдения следующих условий.  
  
- **Равный ранг.** Ранги двух массивов должны быть одинаковыми, то есть они должны иметь одинаковое количество измерений. Однако длины соответствующих измерений не обязательно должны совпадать.  
  
- **Тип данных элемента.** Типы данных элементов обоих массивов должны быть ссылочными типами. Нельзя преобразовать `Integer` массив в `Long` массив или даже в `Object` массив, поскольку задействован хотя бы один тип значения. Дополнительные сведения см. в разделе [типы значений и ссылочные типы](value-types-and-reference-types.md).  
  
- **Вариантное.** Преобразование (расширяющее или сужение) должно быть возможным между типами элементов двух массивов. Пример, в котором не выполняется это требование — попытка преобразования между `String` массивом и массивом класса, производного от <xref:System.Attribute?displayProperty=nameWithType> . Эти два типа не имеют ничего общего, и между ними не существует каких либо преобразований.  
  
 Преобразование одного типа массива в другой может расширяться или уменьшаться в зависимости от того, является ли преобразование соответствующих элементов расширяющим или узким. Для получения дополнительной информации см. [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Преобразование в массив объектов  

 Если массив объявляется `Object` без инициализации, его тип элемента будет таким, `Object` пока он остается неинициализированным. При присвоении значения массиву определенного класса он принимает тип этого класса. Однако его базовый тип по-прежнему остается `Object` , и впоследствии его можно установить в другой массив несвязанного класса. Поскольку все классы являются производными от `Object` , можно изменить тип элемента массива с любого класса на любой другой класс.  
  
 В следующем примере не существует преобразования между типами `student` и `String` , но оба являются производными от `Object` , поэтому все назначения являются допустимыми.  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a>Базовый тип массива  

 Если изначально был объявлен массив с конкретным классом, его базовым типом элемента является этот класс. Если впоследствии задать для него массив другого класса, необходимо выполнить преобразование между двумя классами.  
  
 В следующем примере `students` — это `student` массив. Так как преобразование между и не существует `String` `student` , последняя инструкция завершается ошибкой.  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>См. также

- [Типы данных](index.md)
- [Преобразование типов в Visual Basic](type-conversions.md)
- [Явные и неявные преобразования](implicit-and-explicit-conversions.md)
- [Преобразования значений между строковыми и другими типами](conversions-between-strings-and-other-types.md)
- [Практическое руководство. Преобразование объекта к другому типу в Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Типы данных](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
- [Массивы](../arrays/index.md)
