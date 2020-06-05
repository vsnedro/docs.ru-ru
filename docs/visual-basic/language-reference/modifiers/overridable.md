---
title: Overridable
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: dcbabde8464dd8a0ce5fad24d7d72b1e780270d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392123"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="d2276-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2276-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="d2276-103">Указывает, что свойство или процедура может быть переопределена свойством или процедурой с идентичным именем в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d2276-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2276-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d2276-104">Remarks</span></span>  
 <span data-ttu-id="d2276-105">`Overridable`Модификатор позволяет переопределять свойство или метод в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d2276-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="d2276-106">Модификатор [NotOverridable](notoverridable.md) предотвращает переопределение свойства или метода в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d2276-106">The [NotOverridable](notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="d2276-107">Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d2276-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="d2276-108">Если `Overridable` Модификатор или `NotOverridable` не задан, значение по умолчанию зависит от того, переопределяет ли свойство или метод свойство или метод базового класса.</span><span class="sxs-lookup"><span data-stu-id="d2276-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="d2276-109">Если свойство или метод переопределяет свойство или метод базового класса, параметр по умолчанию имеет значение `Overridable` ; в противном случае — `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="d2276-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="d2276-110">Можно выполнить затенение или переопределение, чтобы переопределить наследуемый элемент, но существуют значительные различия между этими двумя подходами.</span><span class="sxs-lookup"><span data-stu-id="d2276-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="d2276-111">Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="d2276-111">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="d2276-112">Элемент, который можно переопределить, иногда называется *виртуальным* элементом.</span><span class="sxs-lookup"><span data-stu-id="d2276-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="d2276-113">Если он может быть переопределен, но не обязательно должен быть, он иногда также называется *конкретным* элементом.</span><span class="sxs-lookup"><span data-stu-id="d2276-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="d2276-114">Можно использовать `Overridable` только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="d2276-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="d2276-115">Комбинированные модификаторы</span><span class="sxs-lookup"><span data-stu-id="d2276-115">Combined Modifiers</span></span>  
 <span data-ttu-id="d2276-116">Нельзя указывать `Overridable` или `NotOverridable` для `Private` метода.</span><span class="sxs-lookup"><span data-stu-id="d2276-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="d2276-117">Нельзя указывать `Overridable` вместе с `MustOverride` , `NotOverridable` или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="d2276-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="d2276-118">Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="d2276-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="d2276-119">Использование</span><span class="sxs-lookup"><span data-stu-id="d2276-119">Usage</span></span>  
 <span data-ttu-id="d2276-120">Модификатор `Overridable` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="d2276-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d2276-121">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="d2276-121">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="d2276-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d2276-122">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="d2276-123">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="d2276-123">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d2276-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2276-124">See also</span></span>

- [<span data-ttu-id="d2276-125">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="d2276-125">Modifiers</span></span>](index.md)
- [<span data-ttu-id="d2276-126">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="d2276-126">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="d2276-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="d2276-127">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="d2276-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="d2276-128">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="d2276-129">Переопределения</span><span class="sxs-lookup"><span data-stu-id="d2276-129">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="d2276-130">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d2276-130">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="d2276-131">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2276-131">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
