---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 48261e27de302c1809c9725e6e2fc0705a803930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386780"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="99c7e-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99c7e-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="99c7e-103">Указывает, что одна или несколько объявленных переменных-членов ссылаются на экземпляр класса, который может создавать события.</span><span class="sxs-lookup"><span data-stu-id="99c7e-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="99c7e-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="99c7e-104">Remarks</span></span>

<span data-ttu-id="99c7e-105">Если переменная определена с помощью `WithEvents` , можно декларативно указать, что метод обрабатывает события переменной с помощью `Handles` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="99c7e-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="99c7e-106">Можно использовать `WithEvents` только на уровне класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="99c7e-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="99c7e-107">Это означает, что контекст объявления для `WithEvents` переменной должен быть классом или модулем и не может быть исходным файлом, пространством имен, структурой или процедурой.</span><span class="sxs-lookup"><span data-stu-id="99c7e-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="99c7e-108">Нельзя использовать `WithEvents` в члене структуры.</span><span class="sxs-lookup"><span data-stu-id="99c7e-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="99c7e-109">Можно объявлять только отдельные переменные, а не массивы, с помощью `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="99c7e-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="99c7e-110">Правила</span><span class="sxs-lookup"><span data-stu-id="99c7e-110">Rules</span></span>

<span data-ttu-id="99c7e-111">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="99c7e-111">**Element Types.**</span></span> <span data-ttu-id="99c7e-112">Переменные должны быть объявлены как `WithEvents` переменные объекта, чтобы они могли принимать экземпляры класса.</span><span class="sxs-lookup"><span data-stu-id="99c7e-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="99c7e-113">Однако их нельзя объявить как `Object` .</span><span class="sxs-lookup"><span data-stu-id="99c7e-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="99c7e-114">Их необходимо объявить в качестве конкретного класса, который может вызывать события.</span><span class="sxs-lookup"><span data-stu-id="99c7e-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="99c7e-115">`WithEvents`Модификатор можно использовать в этом контексте: [оператор Dim](../statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="99c7e-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="99c7e-116">Пример</span><span class="sxs-lookup"><span data-stu-id="99c7e-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="99c7e-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="99c7e-117">See also</span></span>

- [<span data-ttu-id="99c7e-118">Маркеры</span><span class="sxs-lookup"><span data-stu-id="99c7e-118">Handles</span></span>](../statements/handles-clause.md)
- [<span data-ttu-id="99c7e-119">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="99c7e-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="99c7e-120">События</span><span class="sxs-lookup"><span data-stu-id="99c7e-120">Events</span></span>](../../programming-guide/language-features/events/index.md)
