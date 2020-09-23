---
title: Не удалось получить полное имя операционной системы из-за внутренней ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 744d549b9313727af2feb82e45c24b729cae7262
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079091"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="216ce-102">Не удалось получить полное имя операционной системы из-за внутренней ошибки</span><span class="sxs-lookup"><span data-stu-id="216ce-102">Could not obtain full operation system name due to internal error</span></span>

<span data-ttu-id="216ce-103">Не удалось получить полное имя операционной системы из-за внутренней ошибки.</span><span class="sxs-lookup"><span data-stu-id="216ce-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="216ce-104">Это может быть вызвано отсутствием WMI на текущем компьютере.</span><span class="sxs-lookup"><span data-stu-id="216ce-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="216ce-105">Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="216ce-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="216ce-106">Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="216ce-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="216ce-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="216ce-107">To correct this error</span></span>  
  
1. <span data-ttu-id="216ce-108">Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="216ce-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="216ce-109">Дополнительные сведения об инструментарии WMI и способах его установки см. в статье "инструментарий управления Windows (WMI) Core".</span><span class="sxs-lookup"><span data-stu-id="216ce-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216ce-110">См. также</span><span class="sxs-lookup"><span data-stu-id="216ce-110">See also</span></span>

- [<span data-ttu-id="216ce-111">My. Computer. info. OSFullName</span><span class="sxs-lookup"><span data-stu-id="216ce-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="216ce-112">Обработка и создание исключений в .NET</span><span class="sxs-lookup"><span data-stu-id="216ce-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="216ce-113">Попробуйте... Перехватить... Оператор finally</span><span class="sxs-lookup"><span data-stu-id="216ce-113">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
