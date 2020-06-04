---
title: Практическое руководство. Определение строки, связанной со значением из перечисления
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 525da9206472afefa9f85b49ceee0775cbd168c3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414470"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="edd15-102">Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edd15-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="edd15-103"><xref:System.Enum.GetValues%2A>Методы и <xref:System.Enum.GetNames%2A> позволяют определить строки и значения, связанные с элементами перечисления.</span><span class="sxs-lookup"><span data-stu-id="edd15-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="edd15-104">Определение строки, связанной с перечислением</span><span class="sxs-lookup"><span data-stu-id="edd15-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="edd15-105">Используйте <xref:System.Enum.GetNames%2A> метод для получения строк, связанных с элементами перечисления.</span><span class="sxs-lookup"><span data-stu-id="edd15-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="edd15-106">В этом примере объявляется перечисление, `flavorEnum` а затем используется <xref:System.Enum.GetNames%2A> метод для вывода строк, связанных с каждым элементом.</span><span class="sxs-lookup"><span data-stu-id="edd15-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="edd15-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="edd15-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="edd15-108">Практическое руководство. Объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="edd15-108">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="edd15-109">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="edd15-109">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="edd15-110">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="edd15-110">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="edd15-111">Практическое руководство. Перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edd15-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="edd15-112">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="edd15-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="edd15-113">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="edd15-113">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
