---
title: Преобразования значений между строковыми и другими типами
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 823931f7d6beb8218e8b99d4a8d45716b7214304
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077154"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="202e7-102">Преобразование значений между строковыми и другими типами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="202e7-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>

<span data-ttu-id="202e7-103">Можно преобразовать числовое значение типа, `Boolean` или значения даты и времени в `String` .</span><span class="sxs-lookup"><span data-stu-id="202e7-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="202e7-104">Можно также преобразовать в обратном направлении — от строкового значения к числовому, `Boolean` или `Date` — при условии, что содержимое строки может интерпретироваться как допустимое значение целевого типа данных.</span><span class="sxs-lookup"><span data-stu-id="202e7-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="202e7-105">Если они не могут, возникает ошибка времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="202e7-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="202e7-106">Преобразования для всех этих назначений в любом направлении представляют собой сужающие преобразования.</span><span class="sxs-lookup"><span data-stu-id="202e7-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="202e7-107">Следует использовать ключевые слова преобразования типов (,,,,,,, `CBool` `CByte` ,,,, `CDate` `CDbl` `CDec` `CInt` `CLng` `CSByte` `CShort` `CSng` `CStr` `CUInt` , `CULng` , `CUShort` и `CType` ).</span><span class="sxs-lookup"><span data-stu-id="202e7-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="202e7-108"><xref:Microsoft.VisualBasic.Strings.Format%2A>Функции и <xref:Microsoft.VisualBasic.Conversion.Val%2A> предоставляют дополнительный контроль над преобразованиями между строками и числами.</span><span class="sxs-lookup"><span data-stu-id="202e7-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="202e7-109">Если вы определили класс или структуру, можно определить операторы преобразования типов между `String` и типом класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="202e7-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="202e7-110">Дополнительные сведения см. в разделе [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="202e7-110">For more information, see [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="202e7-111">Преобразование чисел в строки</span><span class="sxs-lookup"><span data-stu-id="202e7-111">Conversion of Numbers to Strings</span></span>  

 <span data-ttu-id="202e7-112">Функцию можно использовать `Format` для преобразования числа в отформатированную строку, которая может включать не только соответствующие цифры, но и символы форматирования, такие как знак валюты (например `$` ,), разделители тысяч или *символы группирования цифр* (например,), `,` и десятичный разделитель (например,) `.` .</span><span class="sxs-lookup"><span data-stu-id="202e7-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="202e7-113">`Format` автоматически использует соответствующие символы в соответствии с **региональными** параметрами, заданными на **панели управления**Windows.</span><span class="sxs-lookup"><span data-stu-id="202e7-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="202e7-114">Обратите внимание, что оператор конкатенации ( `&` ) может преобразовать число в строку неявным образом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="202e7-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="202e7-115">Преобразование строк в числа</span><span class="sxs-lookup"><span data-stu-id="202e7-115">Conversion of Strings to Numbers</span></span>  

 <span data-ttu-id="202e7-116">Функцию можно использовать `Val` для явного преобразования цифр из строки в число.</span><span class="sxs-lookup"><span data-stu-id="202e7-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="202e7-117">`Val` считывает строку, пока не встретится символ, отличный от цифры, пробела, табуляции, перевода строки или точки.</span><span class="sxs-lookup"><span data-stu-id="202e7-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="202e7-118">Последовательности "&O" и "&H" изменяют основание системы счисления и завершают сканирование.</span><span class="sxs-lookup"><span data-stu-id="202e7-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="202e7-119">До тех пор пока не будет остановлено чтение, `Val` преобразует все соответствующие символы в числовое значение.</span><span class="sxs-lookup"><span data-stu-id="202e7-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="202e7-120">Например, следующая инструкция возвращает значение `141.825` .</span><span class="sxs-lookup"><span data-stu-id="202e7-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="202e7-121">Когда Visual Basic преобразует строку в числовое значение, она использует **региональные параметры** , заданные на **панели управления** Windows, для интерпретации разделителя групп разрядов, десятичного разделителя и символа валюты.</span><span class="sxs-lookup"><span data-stu-id="202e7-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="202e7-122">Это означает, что преобразование может быть выполнено в одном параметре, но не в другом.</span><span class="sxs-lookup"><span data-stu-id="202e7-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="202e7-123">Например, `"$14.20"` допустим в английской (США) национальной настройке, но не на французском языке.</span><span class="sxs-lookup"><span data-stu-id="202e7-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="202e7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="202e7-124">See also</span></span>

- [<span data-ttu-id="202e7-125">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="202e7-125">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="202e7-126">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="202e7-126">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="202e7-127">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="202e7-127">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="202e7-128">Практическое руководство. Преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="202e7-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="202e7-129">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="202e7-129">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="202e7-130">Типы данных</span><span class="sxs-lookup"><span data-stu-id="202e7-130">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="202e7-131">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="202e7-131">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="202e7-132">Разработка глобализованных и локализованных приложений</span><span class="sxs-lookup"><span data-stu-id="202e7-132">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
