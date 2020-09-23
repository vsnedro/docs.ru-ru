---
title: Практическое руководство. Перебор элементов перечисления
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 21c170d4708b90987a3f1e9c18969b8803fcdbe0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058720"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="5876c-102">Практическое руководство. Перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5876c-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>

<span data-ttu-id="5876c-103">Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами.</span><span class="sxs-lookup"><span data-stu-id="5876c-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="5876c-104">Чтобы выполнить итерацию по перечислению, можно переместить его в массив с помощью <xref:System.Enum.GetValues%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="5876c-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="5876c-105">Можно также выполнить итерацию перечисления с помощью `For...Each` инструкции, используя <xref:System.Enum.GetNames%2A> <xref:System.Enum.GetValues%2A> метод или для извлечения строкового или числового значения.</span><span class="sxs-lookup"><span data-stu-id="5876c-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="5876c-106">Перебор перечислений</span><span class="sxs-lookup"><span data-stu-id="5876c-106">To iterate through an enumeration</span></span>  
  
- <span data-ttu-id="5876c-107">Объявите массив и преобразуйте перечисление в него с помощью <xref:System.Enum.GetValues%2A> метода, прежде чем передавать массив, как и любую другую переменную.</span><span class="sxs-lookup"><span data-stu-id="5876c-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="5876c-108">В следующем примере отображается каждый элемент перечисления по <xref:Microsoft.VisualBasic.FirstDayOfWeek> мере его итерации по перечислению.</span><span class="sxs-lookup"><span data-stu-id="5876c-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="5876c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5876c-109">See also</span></span>

- [<span data-ttu-id="5876c-110">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="5876c-110">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="5876c-111">Практическое руководство. Объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="5876c-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="5876c-112">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="5876c-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="5876c-113">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="5876c-113">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="5876c-114">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="5876c-114">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="5876c-115">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="5876c-115">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="5876c-116">Массивы</span><span class="sxs-lookup"><span data-stu-id="5876c-116">Arrays</span></span>](../arrays/index.md)
