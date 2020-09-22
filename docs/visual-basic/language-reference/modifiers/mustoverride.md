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
ms.openlocfilehash: cf73f07b6e13d524281129e3c5d8dceceb90764c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867944"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="beedd-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="beedd-102">MustOverride (Visual Basic)</span></span>

<span data-ttu-id="beedd-103">Указывает, что свойство или процедура не реализованы в этом классе и должны быть переопределены в производном классе, прежде чем его можно будет использовать.</span><span class="sxs-lookup"><span data-stu-id="beedd-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beedd-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="beedd-104">Remarks</span></span>  

 <span data-ttu-id="beedd-105">Можно использовать `MustOverride` только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="beedd-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="beedd-106">Свойство или процедура, указывающие, `MustOverride` должен быть членом класса, а класс должен быть помечен как [MustInherit](mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="beedd-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="beedd-107">Правила</span><span class="sxs-lookup"><span data-stu-id="beedd-107">Rules</span></span>  
  
- <span data-ttu-id="beedd-108">**Неполное объявление.**</span><span class="sxs-lookup"><span data-stu-id="beedd-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="beedd-109">При указании `MustOverride` не предоставляется никаких дополнительных строк кода для свойства или процедуры, а не `End Function` `End Property` инструкции, или `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="beedd-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="beedd-110">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="beedd-110">**Combined Modifiers.**</span></span> <span data-ttu-id="beedd-111">Нельзя указывать `MustOverride` вместе с `NotOverridable` , `Overridable` или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="beedd-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="beedd-112">**Сокрытие и переопределение.**</span><span class="sxs-lookup"><span data-stu-id="beedd-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="beedd-113">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="beedd-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="beedd-114">Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="beedd-114">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="beedd-115">**Альтернативные условия.**</span><span class="sxs-lookup"><span data-stu-id="beedd-115">**Alternate Terms.**</span></span> <span data-ttu-id="beedd-116">Элемент, который нельзя использовать, за исключением переопределения, иногда называют *чисто виртуальным* элементом.</span><span class="sxs-lookup"><span data-stu-id="beedd-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="beedd-117">Модификатор `MustOverride` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="beedd-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="beedd-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="beedd-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="beedd-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="beedd-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="beedd-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="beedd-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="beedd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="beedd-121">See also</span></span>

- [<span data-ttu-id="beedd-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="beedd-122">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="beedd-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="beedd-123">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="beedd-124">Переопределения</span><span class="sxs-lookup"><span data-stu-id="beedd-124">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="beedd-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="beedd-125">MustInherit</span></span>](mustinherit.md)
- [<span data-ttu-id="beedd-126">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="beedd-126">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="beedd-127">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="beedd-127">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
