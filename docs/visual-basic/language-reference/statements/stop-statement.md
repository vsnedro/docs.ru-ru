---
title: Оператор Stop
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: c9226ccaea9a0709a9d6a49900f69cb9ac9e1dbe
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871738"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="a788d-102">Оператор Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a788d-102">Stop Statement (Visual Basic)</span></span>

<span data-ttu-id="a788d-103">Приостанавливает выполнение.</span><span class="sxs-lookup"><span data-stu-id="a788d-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a788d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a788d-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="a788d-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="a788d-105">Remarks</span></span>  

 <span data-ttu-id="a788d-106">Операторы можно разместить `Stop` в любом месте процедуры, чтобы приостановить выполнение.</span><span class="sxs-lookup"><span data-stu-id="a788d-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="a788d-107">Использование `Stop` инструкции аналогично установке точки останова в коде.</span><span class="sxs-lookup"><span data-stu-id="a788d-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="a788d-108">`Stop`Инструкция приостанавливает выполнение, но в отличие от этого `End` она не закрывает никакие файлы и не очищает переменные, если она не обнаружена в скомпилированном исполняемом файле (exe).</span><span class="sxs-lookup"><span data-stu-id="a788d-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a788d-109">Если `Stop` инструкция обнаружена в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик.</span><span class="sxs-lookup"><span data-stu-id="a788d-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="a788d-110">Это справедливо независимо от того, был ли код скомпилирован в режиме отладки или розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="a788d-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a788d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a788d-111">Example</span></span>  

 <span data-ttu-id="a788d-112">В этом примере используется `Stop` оператор для приостановки выполнения для каждой итерации в `For...Next` цикле.</span><span class="sxs-lookup"><span data-stu-id="a788d-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="a788d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a788d-113">See also</span></span>

- [<span data-ttu-id="a788d-114">Оператор End</span><span class="sxs-lookup"><span data-stu-id="a788d-114">End Statement</span></span>](end-statement.md)
