---
title: Функции обратного вызова
description: Узнайте о функциях обратного вызова, который представляют собой код в управляемом приложении, помогающий неуправляемой функции DLL выполнить задачу.
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
ms.openlocfilehash: e28756b5ed935aff83363b38d6f33982e87718b2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621721"
---
# <a name="callback-functions"></a><span data-ttu-id="28829-103">Функции обратного вызова</span><span class="sxs-lookup"><span data-stu-id="28829-103">Callback Functions</span></span>
<span data-ttu-id="28829-104">Функция обратного вызова — это программный код в управляемом приложении, который помогает неуправляемой функции DLL выполнить задачу.</span><span class="sxs-lookup"><span data-stu-id="28829-104">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="28829-105">Вызовы функции обратного вызова косвенно, через функцию DLL, передаются из управляемого приложения и возвращаются в управляемую реализацию.</span><span class="sxs-lookup"><span data-stu-id="28829-105">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="28829-106">Лишь некоторые из многих функций DLL, вызываемых в вызове неуправляемого кода, требуют для своего выполнения наличия в управляемом коде функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="28829-106">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="28829-107">Для вызова большинства функций DLL из управляемого кода нужно создать управляемое определение функции и затем выполнить сам вызов.</span><span class="sxs-lookup"><span data-stu-id="28829-107">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="28829-108">Этот процесс достаточно прост.</span><span class="sxs-lookup"><span data-stu-id="28829-108">The process is straightforward.</span></span>  
  
 <span data-ttu-id="28829-109">Применение функции DLL, требующей наличия функции обратного вызова, предполагает выполнение некоторых дополнительных шагов.</span><span class="sxs-lookup"><span data-stu-id="28829-109">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="28829-110">Во-первых, необходимо определить, требуется ли для функции обратный вызов. Это можно выяснить в документации по функции.</span><span class="sxs-lookup"><span data-stu-id="28829-110">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="28829-111">Далее нужно создать функцию обратного вызова в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="28829-111">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="28829-112">И, наконец, вы вызываете функцию DLL, передавая указатель на функцию обратного вызова в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="28829-112">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span>

 <span data-ttu-id="28829-113">На рисунке ниже показана функция обратного вызова и этапы ее реализации:</span><span class="sxs-lookup"><span data-stu-id="28829-113">The following illustration summarizes the callback function and implementation steps:</span></span>  
  
 ![Схема, иллюстрирующая процесс обратного вызова неуправляемого кода.](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 <span data-ttu-id="28829-115">Функции обратного вызова — идеальное средство для многократного выполнения некоторой задачи.</span><span class="sxs-lookup"><span data-stu-id="28829-115">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="28829-116">Другая область их применения — с функциями перечисления API Windows, такими как **EnumFontFamilies**, **EnumPrinters** и **EnumWindows**.</span><span class="sxs-lookup"><span data-stu-id="28829-116">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Windows API.</span></span> <span data-ttu-id="28829-117">Функция **EnumWindows** выполняет перечисление всех существующих на компьютере окон, используя функцию обратного вызова, чтобы выполнить задачу для каждого окна.</span><span class="sxs-lookup"><span data-stu-id="28829-117">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="28829-118">Инструкции и примеры см. в разделе [Практическое руководство. Реализация функций обратного вызова](how-to-implement-callback-functions.md).</span><span class="sxs-lookup"><span data-stu-id="28829-118">For instructions and an example, see [How to: Implement Callback Functions](how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28829-119">См. также</span><span class="sxs-lookup"><span data-stu-id="28829-119">See also</span></span>

- [<span data-ttu-id="28829-120">Практическое руководство. Реализация функций обратного вызова</span><span class="sxs-lookup"><span data-stu-id="28829-120">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)
- [<span data-ttu-id="28829-121">Вызов функции DLL</span><span class="sxs-lookup"><span data-stu-id="28829-121">Calling a DLL Function</span></span>](calling-a-dll-function.md)
