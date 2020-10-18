---
title: События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 02039b81251e59a951a0fe37ec2c9534b458b6a5
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161924"
---
# <a name="bc30594-events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="de2c7-102">BC30594: события общих переменных WithEvents не могут обрабатываться методами, не являющимися общими</span><span class="sxs-lookup"><span data-stu-id="de2c7-102">BC30594: Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>

<span data-ttu-id="de2c7-103">Переменная, объявленная с `Shared` модификатором, является общей переменной.</span><span class="sxs-lookup"><span data-stu-id="de2c7-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="de2c7-104">Общая переменная определяет ровно одно место хранения.</span><span class="sxs-lookup"><span data-stu-id="de2c7-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="de2c7-105">Переменная, объявленная с `WithEvents` модификатором, утверждает, что тип, которому принадлежит переменная, обрабатывает набор событий, которые создает переменная.</span><span class="sxs-lookup"><span data-stu-id="de2c7-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="de2c7-106">Если переменной присвоено значение, то свойство, созданное `WithEvents` объявлением, отсоединяется от любого существующего обработчика событий и подключается к новому обработчику событий с помощью `Add` метода.</span><span class="sxs-lookup"><span data-stu-id="de2c7-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>

 <span data-ttu-id="de2c7-107">**Идентификатор ошибки:** BC30594</span><span class="sxs-lookup"><span data-stu-id="de2c7-107">**Error ID:** BC30594</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="de2c7-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="de2c7-108">To correct this error</span></span>

- <span data-ttu-id="de2c7-109">Объявите обработчик событий `Shared` .</span><span class="sxs-lookup"><span data-stu-id="de2c7-109">Declare your event handler `Shared`.</span></span>

## <a name="see-also"></a><span data-ttu-id="de2c7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="de2c7-110">See also</span></span>

- [<span data-ttu-id="de2c7-111">Общий</span><span class="sxs-lookup"><span data-stu-id="de2c7-111">Shared</span></span>](../modifiers/shared.md)
- [<span data-ttu-id="de2c7-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="de2c7-112">WithEvents</span></span>](../modifiers/withevents.md)
