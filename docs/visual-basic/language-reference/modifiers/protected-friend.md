---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 202d4f4a3a05a64ab1d74621268f28f6b55e8952
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404840"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="596dd-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="596dd-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="596dd-103">Комбинация ключевых слов `Protected Friend` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="596dd-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="596dd-104">Он предоставляет [дружественный](friend.md) доступ и [защищенный](protected.md) доступ к объявленным элементам, поэтому они доступны из любого места в одной сборке, из их собственного класса и из производных классов.</span><span class="sxs-lookup"><span data-stu-id="596dd-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="596dd-105">Можно указать `Protected Friend` только для членов классов. нельзя применять `Protected Friend` к членам структуры, поскольку структуры не наследуются.</span><span class="sxs-lookup"><span data-stu-id="596dd-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="596dd-106">В Visual Studio выберите Справка F1 в справке `protected friend` для [защищенного](protected.md) или [дружественного](friend.md)доступа.</span><span class="sxs-lookup"><span data-stu-id="596dd-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="596dd-107">Интегрированная среда разработки выбирает один маркер под курсором, а не составное слово.</span><span class="sxs-lookup"><span data-stu-id="596dd-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="596dd-108">Правила</span><span class="sxs-lookup"><span data-stu-id="596dd-108">Rules</span></span>

<span data-ttu-id="596dd-109">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="596dd-109">**Declaration Context.**</span></span> <span data-ttu-id="596dd-110">Можно использовать `Protected Friend` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="596dd-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="596dd-111">Это означает, что контекст объявления для `Protected` элемента должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.</span><span class="sxs-lookup"><span data-stu-id="596dd-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="596dd-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="596dd-112">See also</span></span>

- [<span data-ttu-id="596dd-113">Открытый</span><span class="sxs-lookup"><span data-stu-id="596dd-113">Public</span></span>](public.md)
- [<span data-ttu-id="596dd-114">От</span><span class="sxs-lookup"><span data-stu-id="596dd-114">Protected</span></span>](protected.md)
- [<span data-ttu-id="596dd-115">Объявление</span><span class="sxs-lookup"><span data-stu-id="596dd-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="596dd-116">Частное</span><span class="sxs-lookup"><span data-stu-id="596dd-116">Private</span></span>](private.md)
- [<span data-ttu-id="596dd-117">Частный защищенный</span><span class="sxs-lookup"><span data-stu-id="596dd-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="596dd-118">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="596dd-118">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="596dd-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="596dd-119">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="596dd-120">Структуры</span><span class="sxs-lookup"><span data-stu-id="596dd-120">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="596dd-121">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="596dd-121">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
