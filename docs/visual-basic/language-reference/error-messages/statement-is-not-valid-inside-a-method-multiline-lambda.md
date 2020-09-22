---
title: Оператор недопустим в теле метода/многострочного лямбда-оператора
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: d5d756f1772b9519613e163119b88a3057d36cf3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870623"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="f020e-102">Оператор недопустим в теле метода/многострочного лямбда-оператора</span><span class="sxs-lookup"><span data-stu-id="f020e-102">Statement is not valid inside a method/multiline lambda</span></span>

<span data-ttu-id="f020e-103">Оператор недопустим в `Sub` `Function` процедуре свойства,, свойства `Get` или `Set` .</span><span class="sxs-lookup"><span data-stu-id="f020e-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="f020e-104">Некоторые инструкции можно разместить на уровне модуля или класса.</span><span class="sxs-lookup"><span data-stu-id="f020e-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="f020e-105">Другие, такие как `Option Strict` , должны находиться на уровне пространства имен и предшествовать всем остальным объявлениям.</span><span class="sxs-lookup"><span data-stu-id="f020e-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="f020e-106">**Идентификатор ошибки:** BC30024</span><span class="sxs-lookup"><span data-stu-id="f020e-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f020e-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f020e-107">To correct this error</span></span>  
  
- <span data-ttu-id="f020e-108">Удалите инструкцию из процедуры.</span><span class="sxs-lookup"><span data-stu-id="f020e-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f020e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f020e-109">See also</span></span>

- [<span data-ttu-id="f020e-110">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="f020e-110">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="f020e-111">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="f020e-111">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="f020e-112">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="f020e-112">Get Statement</span></span>](../statements/get-statement.md)
- [<span data-ttu-id="f020e-113">Инструкция SET</span><span class="sxs-lookup"><span data-stu-id="f020e-113">Set Statement</span></span>](../statements/set-statement.md)
