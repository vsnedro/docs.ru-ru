---
title: Выполнение оператора Resume без ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 6dd6805151de52a5e0cf51c520485c0e8558e0a7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870827"
---
# <a name="resume-without-error"></a><span data-ttu-id="52229-102">Выполнение оператора Resume без ошибки</span><span class="sxs-lookup"><span data-stu-id="52229-102">Resume without error</span></span>

<span data-ttu-id="52229-103">`Resume`Оператор обнаружен за пределами кода обработки ошибок, или код был переведен в обработчик ошибок, несмотря на отсутствие ошибки.</span><span class="sxs-lookup"><span data-stu-id="52229-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="52229-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="52229-104">To correct this error</span></span>  
  
1. <span data-ttu-id="52229-105">Переместите `Resume` оператор в обработчик ошибок или удалите его.</span><span class="sxs-lookup"><span data-stu-id="52229-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="52229-106">Переход к меткам не может осуществляться между процедурами, поэтому выполните поиск по этой процедуре для метки, идентифицирующей обработчик ошибок.</span><span class="sxs-lookup"><span data-stu-id="52229-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="52229-107">Если обнаружена повторяющаяся метка, указанная в качестве целевого объекта `GoTo` инструкции, которая не является `On Error GoTo` инструкцией, измените метку строки, чтобы согласовать ее с предполагаемой целью.</span><span class="sxs-lookup"><span data-stu-id="52229-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52229-108">См. также</span><span class="sxs-lookup"><span data-stu-id="52229-108">See also</span></span>

- [<span data-ttu-id="52229-109">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="52229-109">Resume Statement</span></span>](../statements/resume-statement.md)
- [<span data-ttu-id="52229-110">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="52229-110">On Error Statement</span></span>](../statements/on-error-statement.md)
