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
ms.openlocfilehash: 2ef1e2f9045e5509e11557c9fdaf3edd2786b72c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404230"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="bb25c-102">Оператор Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb25c-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="bb25c-103">Приостанавливает выполнение.</span><span class="sxs-lookup"><span data-stu-id="bb25c-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb25c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb25c-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="bb25c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="bb25c-105">Remarks</span></span>  
 <span data-ttu-id="bb25c-106">Операторы можно разместить `Stop` в любом месте процедуры, чтобы приостановить выполнение.</span><span class="sxs-lookup"><span data-stu-id="bb25c-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="bb25c-107">Использование `Stop` инструкции аналогично установке точки останова в коде.</span><span class="sxs-lookup"><span data-stu-id="bb25c-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="bb25c-108">`Stop`Инструкция приостанавливает выполнение, но в отличие от этого `End` она не закрывает никакие файлы и не очищает переменные, если она не обнаружена в скомпилированном исполняемом файле (exe).</span><span class="sxs-lookup"><span data-stu-id="bb25c-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb25c-109">Если `Stop` инструкция обнаружена в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик.</span><span class="sxs-lookup"><span data-stu-id="bb25c-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="bb25c-110">Это справедливо независимо от того, был ли код скомпилирован в режиме отладки или розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="bb25c-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb25c-111">Пример</span><span class="sxs-lookup"><span data-stu-id="bb25c-111">Example</span></span>  
 <span data-ttu-id="bb25c-112">В этом примере используется `Stop` оператор для приостановки выполнения для каждой итерации в `For...Next` цикле.</span><span class="sxs-lookup"><span data-stu-id="bb25c-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="bb25c-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bb25c-113">See also</span></span>

- [<span data-ttu-id="bb25c-114">End, инструкция</span><span class="sxs-lookup"><span data-stu-id="bb25c-114">End Statement</span></span>](end-statement.md)
