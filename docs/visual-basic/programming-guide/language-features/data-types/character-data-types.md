---
title: Символьные типы данных
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 33dd4c62776ae8c5ec0ce0a6d0858a7ed0d047fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401996"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="a810b-102">Символьные типы данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a810b-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="a810b-103">Visual Basic предоставляет *символьные типы данных* для работы с печатными и отображаемыми символами.</span><span class="sxs-lookup"><span data-stu-id="a810b-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="a810b-104">Несмотря на то, что они работают с символами Юникода, `Char` содержит один символ, тогда как `String` содержит неопределенное число символов.</span><span class="sxs-lookup"><span data-stu-id="a810b-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="a810b-105">Для таблицы, отображающей параллельное сравнение типов данных Visual Basic, см. в разделе [типы данных](../../../language-reference/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="a810b-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="a810b-106">Тип char</span><span class="sxs-lookup"><span data-stu-id="a810b-106">Char Type</span></span>  
 <span data-ttu-id="a810b-107">`Char`Тип данных — это один двухбайтовый (16-разрядный) символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="a810b-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="a810b-108">Если переменная всегда хранит ровно один символ, объявите ее как `Char` .</span><span class="sxs-lookup"><span data-stu-id="a810b-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="a810b-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="a810b-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="a810b-110">Каждое возможное значение в `Char` переменной или `String` является кодовой *точкой*или кодом символа в кодировке Юникода.</span><span class="sxs-lookup"><span data-stu-id="a810b-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="a810b-111">Символы Юникода включают в себя основную кодировку ASCII, различные буквы, цифры, символы валют, дроби, диакритические знаки, математические и технические символы.</span><span class="sxs-lookup"><span data-stu-id="a810b-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a810b-112">Набор символов Юникода резервирует кодовые точки D800 до DFFF (от 55296 до 55551 десятичного) для *пар символов-заместителей*, для которых требуются 2 16-разрядные значения для представления одной кодовой точки.</span><span class="sxs-lookup"><span data-stu-id="a810b-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="a810b-113">`Char`Переменная не может содержать суррогатную пару, а `String` для хранения такой пары используется две позиции.</span><span class="sxs-lookup"><span data-stu-id="a810b-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="a810b-114">Дополнительные сведения см. в разделе [тип данных char](../../../language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="a810b-114">For more information, see [Char Data Type](../../../language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="a810b-115">Тип строки</span><span class="sxs-lookup"><span data-stu-id="a810b-115">String Type</span></span>  
 <span data-ttu-id="a810b-116">`String`Тип данных — это последовательность из нуля или более двухбайтовых (16-разрядных) символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="a810b-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="a810b-117">Если переменная может содержать неопределенное число символов, объявите ее как `String` .</span><span class="sxs-lookup"><span data-stu-id="a810b-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="a810b-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="a810b-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="a810b-119">Дополнительные сведения см. в разделе [тип данных String](../../../language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="a810b-119">For more information, see [String Data Type](../../../language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a810b-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a810b-120">See also</span></span>

- [<span data-ttu-id="a810b-121">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="a810b-121">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="a810b-122">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="a810b-122">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="a810b-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a810b-123">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="a810b-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="a810b-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="a810b-125">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a810b-125">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="a810b-126">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="a810b-126">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="a810b-127">Символы типов</span><span class="sxs-lookup"><span data-stu-id="a810b-127">Type Characters</span></span>](type-characters.md)
