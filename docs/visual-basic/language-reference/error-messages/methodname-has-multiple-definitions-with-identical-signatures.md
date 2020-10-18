---
title: Метод <methodname> несколько раз определен с одинаковыми подписями
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 663b22421d1a0e401cfb3c135c99bd097163a78b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160370"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="d8492-102">BC30269: " \<methodname> " имеет несколько определений с одинаковыми сигнатурами</span><span class="sxs-lookup"><span data-stu-id="d8492-102">BC30269: '\<methodname>' has multiple definitions with identical signatures</span></span>

<span data-ttu-id="d8492-103">В `Function` `Sub` объявлении процедуры или используется то же имя процедуры и список аргументов, что и в предыдущем объявлении.</span><span class="sxs-lookup"><span data-stu-id="d8492-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="d8492-104">Одной из возможных причин является попытка перегрузки исходной процедуры.</span><span class="sxs-lookup"><span data-stu-id="d8492-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="d8492-105">Перегруженные процедуры должны иметь разные списки аргументов.</span><span class="sxs-lookup"><span data-stu-id="d8492-105">Overloaded procedures must have different argument lists.</span></span>

 <span data-ttu-id="d8492-106">**Идентификатор ошибки:** BC30269</span><span class="sxs-lookup"><span data-stu-id="d8492-106">**Error ID:** BC30269</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d8492-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d8492-107">To correct this error</span></span>

- <span data-ttu-id="d8492-108">Измените имя процедуры или список аргументов или удалите повторяющееся объявление.</span><span class="sxs-lookup"><span data-stu-id="d8492-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8492-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d8492-109">See also</span></span>

- [<span data-ttu-id="d8492-110">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="d8492-110">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="d8492-111">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="d8492-111">Considerations in Overloading Procedures</span></span>](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
