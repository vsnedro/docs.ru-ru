---
title: Практическое руководство. Преобразование строки в массив символов
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: e1f634fcdb23f16e794449f8fe7b53c451c8c5b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059175"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="6987c-102">Практическое руководство. Преобразование строки (String) в массив символов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6987c-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>

<span data-ttu-id="6987c-103">Иногда бывает полезно иметь данные о символах в строке и позициях этих символов в строке, например при анализе строки.</span><span class="sxs-lookup"><span data-stu-id="6987c-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="6987c-104">В этом примере показано, как можно получить массив символов в строке, вызвав <xref:System.String.ToCharArray%2A> метод строки.</span><span class="sxs-lookup"><span data-stu-id="6987c-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6987c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="6987c-105">Example</span></span>  

 <span data-ttu-id="6987c-106">В этом примере показано, как разделить строку на `Char` массив и как разбить строку на `String` массив символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="6987c-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="6987c-107">Это различие состоит в том, что символы текста в Юникоде могут состоять из двух или более `Char` символов (например, суррогатной пары или последовательности присоединяемых символов).</span><span class="sxs-lookup"><span data-stu-id="6987c-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="6987c-108">Дополнительные сведения см <xref:System.Globalization.TextElementEnumerator> . в разделе и [стандарт Unicode](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="6987c-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="6987c-109">Пример</span><span class="sxs-lookup"><span data-stu-id="6987c-109">Example</span></span>  

 <span data-ttu-id="6987c-110">Сложнее разбить строку на символы в Юникоде, но это необходимо, если требуются сведения о визуальном представлении строки.</span><span class="sxs-lookup"><span data-stu-id="6987c-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="6987c-111">В этом примере <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> метод используется для получения сведений о символах текста Юникода, составляющих строку.</span><span class="sxs-lookup"><span data-stu-id="6987c-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="6987c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6987c-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="6987c-113">Практическое руководство. Доступ к символам в строках</span><span class="sxs-lookup"><span data-stu-id="6987c-113">How to: Access Characters in Strings</span></span>](how-to-access-characters-in-strings.md)
- [<span data-ttu-id="6987c-114">Преобразование между строками и другими типами данных в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6987c-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="6987c-115">Строки</span><span class="sxs-lookup"><span data-stu-id="6987c-115">Strings</span></span>](index.md)
