---
title: В <name> не найдено доступного метода Main с подходящей подписью
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: e1f95484a153bdcac9543508b7f2708dc6b7d942
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160045"
---
# <a name="bc30737-no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="3ca19-102">BC30737: в "" не найден доступный метод "Main" с подходящей сигнатурой. \<name></span><span class="sxs-lookup"><span data-stu-id="3ca19-102">BC30737: No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>

<span data-ttu-id="3ca19-103">Приложения командной строки должны иметь `Sub Main` определенные.</span><span class="sxs-lookup"><span data-stu-id="3ca19-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="3ca19-104">`Main` должен быть объявлен как `Public Shared` , если он определен в классе, или как, `Public` если он определен в модуле.</span><span class="sxs-lookup"><span data-stu-id="3ca19-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>

 <span data-ttu-id="3ca19-105">**Идентификатор ошибки:** BC30737</span><span class="sxs-lookup"><span data-stu-id="3ca19-105">**Error ID:** BC30737</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3ca19-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3ca19-106">To correct this error</span></span>

- <span data-ttu-id="3ca19-107">Определите `Public Sub Main` процедуру для проекта.</span><span class="sxs-lookup"><span data-stu-id="3ca19-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="3ca19-108">Объявите его как `Shared` If и только в том случае, если оно определено внутри класса.</span><span class="sxs-lookup"><span data-stu-id="3ca19-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ca19-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3ca19-109">See also</span></span>

- [<span data-ttu-id="3ca19-110">Структура программы Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3ca19-110">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="3ca19-111">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3ca19-111">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
