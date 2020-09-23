---
title: Практическое руководство. Группирование значений связанных констант
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 0f694aee722e8ce31f663ec9fe52a09a2eb2a958
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058733"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="f966f-102">Практическое руководство. Группирование значений связанных констант (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f966f-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>

<span data-ttu-id="f966f-103">Перечисление — это лучший способ сгруппировать связанные константы.</span><span class="sxs-lookup"><span data-stu-id="f966f-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="f966f-104">Перечисление создается с помощью `Enum` инструкции в разделе Declarations класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="f966f-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="f966f-105">Дополнительные сведения см. [в разделе инструкции. Объявление перечисления](how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="f966f-105">For more information, see [How to: Declare an Enumeration](how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="f966f-106">Группирование связанных значений констант</span><span class="sxs-lookup"><span data-stu-id="f966f-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="f966f-107">Напишите объявление, которое включает уровень доступа к коду, `Enum` ключевое слово и допустимое имя.</span><span class="sxs-lookup"><span data-stu-id="f966f-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="f966f-108">В этом примере создается `Private` Перечисление `temperatureValues` .</span><span class="sxs-lookup"><span data-stu-id="f966f-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="f966f-109">Определите константы в перечислении.</span><span class="sxs-lookup"><span data-stu-id="f966f-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="f966f-110">В этом примере создается `Public` Перечисление `temperatureValues` , и ему присваиваются значения.</span><span class="sxs-lookup"><span data-stu-id="f966f-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f966f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f966f-111">See also</span></span>

- [<span data-ttu-id="f966f-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="f966f-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="f966f-113">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="f966f-113">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="f966f-114">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="f966f-114">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="f966f-115">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="f966f-115">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="f966f-116">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="f966f-116">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="f966f-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="f966f-117">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
