---
title: Возвращаемые значения функции CStr
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: cc5e5cc437175e9aebfba559488ca74283faa9ad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870157"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Возвращаемые значения функции CStr (Visual Basic)

В следующей таблице описаны возвращаемые значения для `CStr` для различных типов данных `expression` .  
  
|Если `expression` тип —|Возвращаемые значения `CStr`|  
|-----------------------------|--------------------|  
|[Логический тип данных](../data-types/boolean-data-type.md)|Строка, содержащая "true" или "false".|  
|[Тип данных Date](../data-types/date-data-type.md)|Строка, содержащая `Date` значение (Дата и время) в кратком формате даты системы.|  
|[Числовые типы данных](../../programming-guide/language-features/data-types/numeric-data-types.md)|Строка, представляющая число.|  
  
## <a name="cstr-and-date"></a>Функция CStr и Дата  

 `Date`Тип всегда содержит сведения о дате и времени. В целях преобразования типов Visual Basic учитывает 1/1/0001 (1 января 1 года) как *нейтральное значение* для даты, а 00:00:00 (полночь) — как нейтральное значение времени. `CStr` не включает нейтральные значения в результирующую строку. Например, если преобразовать `#January 1, 0001 9:30:00#` в строку, то результатом будет "9:30:00 AM"; сведения о дате подавляются. Однако сведения о дате по-прежнему содержатся в исходном `Date` значении и могут быть восстановлены с помощью таких функций, как <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .  
  
> [!NOTE]
> `CStr`Функция выполняет преобразование на основе текущих настроек языка и региональных параметров для приложения. Чтобы получить строковое представление числа в определенном языке и региональных параметрах, используйте `ToString(IFormatProvider)` метод числа. Например, используйте <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` в `String` .  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Type Conversion Functions](type-conversion-functions.md)
- [Логический тип данных](../data-types/boolean-data-type.md)
- [Тип данных Date](../data-types/date-data-type.md)
