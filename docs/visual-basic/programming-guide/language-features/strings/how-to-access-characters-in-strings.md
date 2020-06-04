---
title: Практическое руководство. Доступ к символам в строках
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: fa5920cfd25f61f6e6c7d5438ef7c0e38a48fa1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401957"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="1c9d1-102">Практическое руководство. Доступ к символам строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c9d1-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="1c9d1-103">В этом примере показано, как использовать <xref:System.String.Chars%2A> свойство для доступа к символу в указанном месте в строке.</span><span class="sxs-lookup"><span data-stu-id="1c9d1-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c9d1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1c9d1-104">Example</span></span>  
 <span data-ttu-id="1c9d1-105">Иногда бывает полезно иметь данные о символах в строке и позициях этих символов в строке.</span><span class="sxs-lookup"><span data-stu-id="1c9d1-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="1c9d1-106">Строку можно представить как массив символов ( `Char` экземпляров); вы можете получить определенный символ, обратившись к индексу этого символа через <xref:System.String.Chars%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="1c9d1-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="1c9d1-107">Параметр свойства отсчитывается `index` <xref:System.String.Chars%2A> от нуля.</span><span class="sxs-lookup"><span data-stu-id="1c9d1-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1c9d1-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="1c9d1-108">Robust Programming</span></span>  
 <span data-ttu-id="1c9d1-109"><xref:System.String.Chars%2A>Свойство возвращает символ в указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="1c9d1-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="1c9d1-110">Однако некоторые символы Юникода могут быть представлены более чем одним символом.</span><span class="sxs-lookup"><span data-stu-id="1c9d1-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="1c9d1-111">Дополнительные сведения о работе с символами Юникода см. в разделе [инструкции. Преобразование строки в массив символов](how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="1c9d1-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="1c9d1-112"><xref:System.String.Chars%2A>Свойство вызывает исключение, <xref:System.IndexOutOfRangeException> Если `index` параметр больше или равен длине строки или если он меньше нуля.</span><span class="sxs-lookup"><span data-stu-id="1c9d1-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9d1-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1c9d1-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="1c9d1-114">Практическое руководство. Преобразование строки в массив символов</span><span class="sxs-lookup"><span data-stu-id="1c9d1-114">How to: Convert a String to an Array of Characters</span></span>](how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="1c9d1-115">Преобразование между строками и другими типами данных в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c9d1-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="1c9d1-116">Строки</span><span class="sxs-lookup"><span data-stu-id="1c9d1-116">Strings</span></span>](index.md)
