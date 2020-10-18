---
title: Структура <structurename> должна содержать по крайней мере один экземпляр переменной члена или экземпляр объявления события, не помеченный как Custom
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 4e7ef82659c43be08ee444eaf3f4df663f7aaa53
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159655"
---
# <a name="bc30941-structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="b6b3a-102">BC30941: структура " \<structurename> " должна содержать по крайней мере одну переменную члена экземпляра или хотя бы одно объявление события экземпляра не помечено как "Custom"</span><span class="sxs-lookup"><span data-stu-id="b6b3a-102">BC30941: Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>

<span data-ttu-id="b6b3a-103">Определение структуры не содержит никаких общих переменных или необщих нестандартных событий.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>

 <span data-ttu-id="b6b3a-104">Каждая структура должна иметь либо переменную, либо событие, которое применяется к каждому конкретному экземпляру (несовместное использование), а не ко всем экземплярам совместно ([Общий](../modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="b6b3a-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../modifiers/shared.md)).</span></span> <span data-ttu-id="b6b3a-105">Необщие константы, свойства и процедуры не соответствуют этому требованию.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="b6b3a-106">Кроме того, если нет необщих переменных и только одно несовместное событие, это событие не может быть `Custom` событием.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>

 <span data-ttu-id="b6b3a-107">**Идентификатор ошибки:** BC30941</span><span class="sxs-lookup"><span data-stu-id="b6b3a-107">**Error ID:** BC30941</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b6b3a-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b6b3a-108">To correct this error</span></span>

- <span data-ttu-id="b6b3a-109">Определите по крайней мере одну переменную или событие, которое не является `Shared` .</span><span class="sxs-lookup"><span data-stu-id="b6b3a-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="b6b3a-110">Если определено только одно событие, оно должно быть нестандартным, а также не общим.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6b3a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b6b3a-111">See also</span></span>

- [<span data-ttu-id="b6b3a-112">Структуры</span><span class="sxs-lookup"><span data-stu-id="b6b3a-112">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="b6b3a-113">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="b6b3a-113">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="b6b3a-114">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="b6b3a-114">Structure Statement</span></span>](../statements/structure-statement.md)
