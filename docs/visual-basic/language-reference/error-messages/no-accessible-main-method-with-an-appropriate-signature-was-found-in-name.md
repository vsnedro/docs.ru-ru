---
title: В <name> не найдено доступного метода Main с подходящей подписью
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6760b931ceb2ad5c2c04169d664da8629badc487
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409417"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="de542-102">В \<name> не найдено доступного метода Main с подходящей подписью</span><span class="sxs-lookup"><span data-stu-id="de542-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="de542-103">Приложения командной строки должны иметь `Sub Main` определенные.</span><span class="sxs-lookup"><span data-stu-id="de542-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="de542-104">`Main`должен быть объявлен как `Public Shared` , если он определен в классе, или как, `Public` если он определен в модуле.</span><span class="sxs-lookup"><span data-stu-id="de542-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="de542-105">**Идентификатор ошибки:** BC30737</span><span class="sxs-lookup"><span data-stu-id="de542-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="de542-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="de542-106">To correct this error</span></span>  
  
- <span data-ttu-id="de542-107">Определите `Public Sub Main` процедуру для проекта.</span><span class="sxs-lookup"><span data-stu-id="de542-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="de542-108">Объявите его как `Shared` If и только в том случае, если оно определено внутри класса.</span><span class="sxs-lookup"><span data-stu-id="de542-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de542-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="de542-109">See also</span></span>

- [<span data-ttu-id="de542-110">Структура программы Visual Basic</span><span class="sxs-lookup"><span data-stu-id="de542-110">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="de542-111">Процедуры</span><span class="sxs-lookup"><span data-stu-id="de542-111">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
