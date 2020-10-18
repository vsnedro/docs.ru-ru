---
title: Оператор недопустим в теле метода/многострочного лямбда-оператора
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef992c3eaa2b82bbf5e8993f9fccd64ae388c95
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159681"
---
# <a name="bc30024-statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="e773d-102">BC30024: недопустимая инструкция в методе или многострочной лямбда-выражении</span><span class="sxs-lookup"><span data-stu-id="e773d-102">BC30024: Statement is not valid inside a method/multiline lambda</span></span>

<span data-ttu-id="e773d-103">Оператор недопустим в `Sub` `Function` процедуре свойства,, свойства `Get` или `Set` .</span><span class="sxs-lookup"><span data-stu-id="e773d-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="e773d-104">Некоторые инструкции можно разместить на уровне модуля или класса.</span><span class="sxs-lookup"><span data-stu-id="e773d-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="e773d-105">Другие, такие как `Option Strict` , должны находиться на уровне пространства имен и предшествовать всем остальным объявлениям.</span><span class="sxs-lookup"><span data-stu-id="e773d-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>

 <span data-ttu-id="e773d-106">**Идентификатор ошибки:** BC30024</span><span class="sxs-lookup"><span data-stu-id="e773d-106">**Error ID:** BC30024</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e773d-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e773d-107">To correct this error</span></span>

- <span data-ttu-id="e773d-108">Удалите инструкцию из процедуры.</span><span class="sxs-lookup"><span data-stu-id="e773d-108">Remove the statement from the procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="e773d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e773d-109">See also</span></span>

- [<span data-ttu-id="e773d-110">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="e773d-110">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="e773d-111">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="e773d-111">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="e773d-112">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="e773d-112">Get Statement</span></span>](../statements/get-statement.md)
- [<span data-ttu-id="e773d-113">Инструкция SET</span><span class="sxs-lookup"><span data-stu-id="e773d-113">Set Statement</span></span>](../statements/set-statement.md)
