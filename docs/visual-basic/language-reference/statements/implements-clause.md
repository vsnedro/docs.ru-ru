---
title: Предложение Implements
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 7c95cf76b1bac24e2a0f20857b8984d54ebbea85
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866166"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="ee263-102">Предложение Implements (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee263-102">Implements Clause (Visual Basic)</span></span>

<span data-ttu-id="ee263-103">Указывает, что член класса или структуры предоставляет реализацию для члена, определенного в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="ee263-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee263-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee263-104">Remarks</span></span>  

<span data-ttu-id="ee263-105">`Implements`Ключевое слово не совпадает с [оператором Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ee263-105">The `Implements` keyword is not the same as the [Implements Statement](implements-statement.md).</span></span> <span data-ttu-id="ee263-106">`Implements`Инструкция используется для указания того, что класс или структура реализует один или несколько интерфейсов, а затем для каждого элемента используется `Implements` ключевое слово для указания интерфейса и члена, который он реализует.</span><span class="sxs-lookup"><span data-stu-id="ee263-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="ee263-107">Если класс или структура реализует интерфейс, он должен включать `Implements` инструкцию сразу после оператора [Class](class-statement.md) или [Structure](structure-statement.md), и она должна реализовывать все члены, определенные интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="ee263-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](class-statement.md) or [Structure Statement](structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="ee263-108">Воссоздании</span><span class="sxs-lookup"><span data-stu-id="ee263-108">Reimplementation</span></span>  

<span data-ttu-id="ee263-109">В производном классе можно повторно реализовать член интерфейса, который уже реализован в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="ee263-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="ee263-110">Это отличается от переопределения члена базового класса в следующих отношениях.</span><span class="sxs-lookup"><span data-stu-id="ee263-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="ee263-111">Член базового класса не обязательно должен быть [переопределяемым](../modifiers/overridable.md) для повторной реализации.</span><span class="sxs-lookup"><span data-stu-id="ee263-111">The base class member does not need to be [Overridable](../modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="ee263-112">Элемент можно повторно реализовать с другим именем.</span><span class="sxs-lookup"><span data-stu-id="ee263-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="ee263-113">`Implements`Ключевое слово можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="ee263-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="ee263-114">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="ee263-114">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="ee263-115">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="ee263-115">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="ee263-116">Property Statement</span><span class="sxs-lookup"><span data-stu-id="ee263-116">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="ee263-117">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="ee263-117">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee263-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ee263-118">See also</span></span>

- [<span data-ttu-id="ee263-119">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="ee263-119">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="ee263-120">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="ee263-120">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="ee263-121">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="ee263-121">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="ee263-122">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="ee263-122">Structure Statement</span></span>](structure-statement.md)
