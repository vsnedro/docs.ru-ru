---
title: Практическое руководство. Ссылка на элемент перечисления
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: d1b239e7d6be3ebf1e64d6589a4cc14dce8946f5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095672"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="c9ac3-102">Практическое руководство. Ссылка на член перечисления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9ac3-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>

<span data-ttu-id="c9ac3-103">Перечисления предоставляют удобный способ работы с наборами связанных констант и для связывания постоянных значений с именами.</span><span class="sxs-lookup"><span data-stu-id="c9ac3-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="c9ac3-104">Например, вы можете объявить перечисление для набора целочисленных констант, связанных с днями недели, а затем использовать в коде названия дней, а не числа.</span><span class="sxs-lookup"><span data-stu-id="c9ac3-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="c9ac3-105">С помощью инструкции можно избежать использования полных имен `Imports` .</span><span class="sxs-lookup"><span data-stu-id="c9ac3-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="c9ac3-106">Дополнительные сведения см. в разделе [перечисления и квалификация имени](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="c9ac3-106">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="c9ac3-107">Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="c9ac3-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="c9ac3-108">Уточните имя члена с помощью перечисления.</span><span class="sxs-lookup"><span data-stu-id="c9ac3-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="c9ac3-109">Например, в следующем примере член перечисления присваивается `Saturday` `FirstDayOfWeek` переменной `DayValue` .</span><span class="sxs-lookup"><span data-stu-id="c9ac3-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="c9ac3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c9ac3-110">See also</span></span>

- [<span data-ttu-id="c9ac3-111">Практическое руководство. Объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="c9ac3-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="c9ac3-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="c9ac3-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="c9ac3-113">Практическое руководство. Перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9ac3-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="c9ac3-114">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="c9ac3-114">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="c9ac3-115">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="c9ac3-115">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
