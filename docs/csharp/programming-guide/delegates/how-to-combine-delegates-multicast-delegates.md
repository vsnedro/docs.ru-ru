---
title: Объединение делегатов (многоадресные делегаты) (руководство по программированию на C#)
description: Узнайте, как объединить делегаты для создания многоадресных делегатов. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d23ea758c9da2c3399f5d98e81360cc250b428a1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302741"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="c1cfd-104">Практическое руководство. Объединение делегатов (многоадресные делегаты) (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="c1cfd-104">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>
<span data-ttu-id="c1cfd-105">В этом примере показано создание многоадресных делегатов.</span><span class="sxs-lookup"><span data-stu-id="c1cfd-105">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="c1cfd-106">Объекты [делегатов](../../language-reference/builtin-types/reference-types.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="c1cfd-106">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="c1cfd-107">Многоадресный делегат содержит список присвоенных ему делегатов.</span><span class="sxs-lookup"><span data-stu-id="c1cfd-107">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="c1cfd-108">При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты.</span><span class="sxs-lookup"><span data-stu-id="c1cfd-108">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="c1cfd-109">Объединять можно только делегаты одного типа.</span><span class="sxs-lookup"><span data-stu-id="c1cfd-109">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="c1cfd-110">С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.</span><span class="sxs-lookup"><span data-stu-id="c1cfd-110">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1cfd-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c1cfd-111">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="c1cfd-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c1cfd-112">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="c1cfd-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c1cfd-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c1cfd-114">События</span><span class="sxs-lookup"><span data-stu-id="c1cfd-114">Events</span></span>](../events/index.md)
