---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: c2dcb044d04099c51f57d82a8bc08f0932bf3542
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875417"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="c6e41-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6e41-102">WithEvents (Visual Basic)</span></span>

<span data-ttu-id="c6e41-103">Указывает, что одна или несколько объявленных переменных-членов ссылаются на экземпляр класса, который может создавать события.</span><span class="sxs-lookup"><span data-stu-id="c6e41-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6e41-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="c6e41-104">Remarks</span></span>

<span data-ttu-id="c6e41-105">Если переменная определена с помощью `WithEvents` , можно декларативно указать, что метод обрабатывает события переменной с помощью `Handles` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="c6e41-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="c6e41-106">Можно использовать `WithEvents` только на уровне класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="c6e41-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="c6e41-107">Это означает, что контекст объявления для `WithEvents` переменной должен быть классом или модулем и не может быть исходным файлом, пространством имен, структурой или процедурой.</span><span class="sxs-lookup"><span data-stu-id="c6e41-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="c6e41-108">Нельзя использовать `WithEvents` в члене структуры.</span><span class="sxs-lookup"><span data-stu-id="c6e41-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="c6e41-109">Можно объявлять только отдельные переменные, а не массивы, с помощью `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="c6e41-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="c6e41-110">Правила</span><span class="sxs-lookup"><span data-stu-id="c6e41-110">Rules</span></span>

<span data-ttu-id="c6e41-111">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="c6e41-111">**Element Types.**</span></span> <span data-ttu-id="c6e41-112">Переменные должны быть объявлены как `WithEvents` переменные объекта, чтобы они могли принимать экземпляры класса.</span><span class="sxs-lookup"><span data-stu-id="c6e41-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="c6e41-113">Однако их нельзя объявить как `Object` .</span><span class="sxs-lookup"><span data-stu-id="c6e41-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="c6e41-114">Их необходимо объявить в качестве конкретного класса, который может вызывать события.</span><span class="sxs-lookup"><span data-stu-id="c6e41-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="c6e41-115">`WithEvents`Модификатор можно использовать в этом контексте: [оператор Dim](../statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c6e41-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="c6e41-116">Пример</span><span class="sxs-lookup"><span data-stu-id="c6e41-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="c6e41-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c6e41-117">See also</span></span>

- [<span data-ttu-id="c6e41-118">Маркеры</span><span class="sxs-lookup"><span data-stu-id="c6e41-118">Handles</span></span>](../statements/handles-clause.md)
- [<span data-ttu-id="c6e41-119">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="c6e41-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="c6e41-120">События</span><span class="sxs-lookup"><span data-stu-id="c6e41-120">Events</span></span>](../../programming-guide/language-features/events/index.md)
