---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 8eec54a12c7fb748df46e8c48a8b07eab983cc72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867870"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="d1335-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1335-102">NotOverridable (Visual Basic)</span></span>

<span data-ttu-id="d1335-103">Указывает, что свойство или процедура не могут быть переопределены в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d1335-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1335-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="d1335-104">Remarks</span></span>  

 <span data-ttu-id="d1335-105">`NotOverridable`Модификатор предотвращает переопределение свойства или метода в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d1335-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="d1335-106">Модификатор [Overridable](overridable.md) позволяет переопределять свойство или метод в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d1335-106">The [Overridable](overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="d1335-107">Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d1335-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="d1335-108">Если `Overridable` Модификатор или `NotOverridable` не задан, значение по умолчанию зависит от того, переопределяет ли свойство или метод свойство или метод базового класса.</span><span class="sxs-lookup"><span data-stu-id="d1335-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="d1335-109">Если свойство или метод переопределяет свойство или метод базового класса, параметр по умолчанию имеет значение `Overridable` ; в противном случае — `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="d1335-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="d1335-110">Элемент, который не может быть переопределен, иногда называется *запечатанным* элементом.</span><span class="sxs-lookup"><span data-stu-id="d1335-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="d1335-111">Можно использовать `NotOverridable` только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="d1335-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="d1335-112">Можно указать `NotOverridable` только для свойства или процедуры, которые переопределяют другое свойство или процедуру, то есть только в сочетании с `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="d1335-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="d1335-113">Комбинированные модификаторы</span><span class="sxs-lookup"><span data-stu-id="d1335-113">Combined Modifiers</span></span>  

 <span data-ttu-id="d1335-114">Нельзя указывать `Overridable` или `NotOverridable` для `Private` метода.</span><span class="sxs-lookup"><span data-stu-id="d1335-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="d1335-115">Нельзя указывать `NotOverridable` вместе с `MustOverride` , `Overridable` или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="d1335-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="d1335-116">Использование</span><span class="sxs-lookup"><span data-stu-id="d1335-116">Usage</span></span>  

 <span data-ttu-id="d1335-117">Модификатор `NotOverridable` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="d1335-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d1335-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="d1335-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="d1335-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d1335-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="d1335-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="d1335-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d1335-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d1335-121">See also</span></span>

- [<span data-ttu-id="d1335-122">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="d1335-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="d1335-123">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="d1335-123">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="d1335-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="d1335-124">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="d1335-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="d1335-125">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="d1335-126">Переопределения</span><span class="sxs-lookup"><span data-stu-id="d1335-126">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="d1335-127">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d1335-127">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="d1335-128">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1335-128">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
