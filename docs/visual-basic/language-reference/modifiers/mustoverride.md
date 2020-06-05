---
title: MustOverride
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: 1b20108a2d42e82c0af7598fde8d60a08fea28ec
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396198"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="e7e38-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7e38-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="e7e38-103">Указывает, что свойство или процедура не реализованы в этом классе и должны быть переопределены в производном классе, прежде чем его можно будет использовать.</span><span class="sxs-lookup"><span data-stu-id="e7e38-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7e38-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e7e38-104">Remarks</span></span>  
 <span data-ttu-id="e7e38-105">Можно использовать `MustOverride` только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="e7e38-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="e7e38-106">Свойство или процедура, указывающие, `MustOverride` должен быть членом класса, а класс должен быть помечен как [MustInherit](mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="e7e38-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e7e38-107">Правила</span><span class="sxs-lookup"><span data-stu-id="e7e38-107">Rules</span></span>  
  
- <span data-ttu-id="e7e38-108">**Неполное объявление.**</span><span class="sxs-lookup"><span data-stu-id="e7e38-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="e7e38-109">При указании `MustOverride` не предоставляется никаких дополнительных строк кода для свойства или процедуры, а не `End Function` `End Property` инструкции, или `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="e7e38-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="e7e38-110">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="e7e38-110">**Combined Modifiers.**</span></span> <span data-ttu-id="e7e38-111">Нельзя указывать `MustOverride` вместе с `NotOverridable` , `Overridable` или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="e7e38-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="e7e38-112">**Сокрытие и переопределение.**</span><span class="sxs-lookup"><span data-stu-id="e7e38-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="e7e38-113">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="e7e38-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="e7e38-114">Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="e7e38-114">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="e7e38-115">**Альтернативные условия.**</span><span class="sxs-lookup"><span data-stu-id="e7e38-115">**Alternate Terms.**</span></span> <span data-ttu-id="e7e38-116">Элемент, который нельзя использовать, за исключением переопределения, иногда называют *чисто виртуальным* элементом.</span><span class="sxs-lookup"><span data-stu-id="e7e38-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="e7e38-117">Модификатор `MustOverride` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="e7e38-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e7e38-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="e7e38-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="e7e38-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="e7e38-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="e7e38-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="e7e38-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7e38-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e7e38-121">See also</span></span>

- [<span data-ttu-id="e7e38-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e7e38-122">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="e7e38-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="e7e38-123">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="e7e38-124">Переопределения</span><span class="sxs-lookup"><span data-stu-id="e7e38-124">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="e7e38-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="e7e38-125">MustInherit</span></span>](mustinherit.md)
- [<span data-ttu-id="e7e38-126">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e7e38-126">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="e7e38-127">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7e38-127">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
