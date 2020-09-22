---
title: Оператор Resume
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: db9d47798d087d60f4318b06fe3291fb895e6618
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871877"
---
# <a name="resume-statement"></a><span data-ttu-id="b4093-102">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="b4093-102">Resume Statement</span></span>

<span data-ttu-id="b4093-103">Возобновляет выполнение по завершении подпрограммы обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="b4093-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="b4093-104">Мы рекомендуем использовать структурированную обработку исключений в коде, когда это возможно, вместо использования неструктурированной обработки исключений и `On Error` `Resume` инструкций и.</span><span class="sxs-lookup"><span data-stu-id="b4093-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="b4093-105">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b4093-105">For more information, see [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4093-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4093-106">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b4093-107">Компоненты</span><span class="sxs-lookup"><span data-stu-id="b4093-107">Parts</span></span>  

 `Resume`  
 <span data-ttu-id="b4093-108">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b4093-108">Required.</span></span> <span data-ttu-id="b4093-109">Если ошибка произошла в той же процедуре, что и обработчик ошибок, выполнение возобновляется с помощью инструкции, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="b4093-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="b4093-110">Если ошибка произошла в вызванной процедуре, выполнение возобновляется с оператора, который последний раз вызывался из процедуры, содержащей подпрограмму обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="b4093-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="b4093-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b4093-111">Optional.</span></span> <span data-ttu-id="b4093-112">Если ошибка произошла в той же процедуре, что и обработчик ошибок, выполнение возобновляется с помощью инструкции, следующей за инструкцией, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="b4093-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="b4093-113">Если ошибка произошла в вызванной процедуре, выполнение возобновляется с помощью инструкции, следующей за инструкцией, которая последний раз вызвала процедуру, содержащую подпрограмму обработки ошибок (или `On Error Resume Next` ).</span><span class="sxs-lookup"><span data-stu-id="b4093-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="b4093-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b4093-114">Optional.</span></span> <span data-ttu-id="b4093-115">Выполнение возобновляется в строке, указанной в `line` аргументе Required.</span><span class="sxs-lookup"><span data-stu-id="b4093-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="b4093-116">`line`Аргумент является меткой строки или номером строки и должен находиться в той же процедуре, что и обработчик ошибок.</span><span class="sxs-lookup"><span data-stu-id="b4093-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4093-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4093-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4093-118">Рекомендуется использовать структурированную обработку исключений в коде, когда это возможно, вместо использования неструктурированной обработки исключений и `On Error` `Resume` инструкций и.</span><span class="sxs-lookup"><span data-stu-id="b4093-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="b4093-119">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b4093-119">For more information, see [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="b4093-120">При использовании `Resume` инструкции в любом месте, кроме в подпрограммы обработки ошибок, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="b4093-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="b4093-121">`Resume`Инструкция не может быть использована в любой процедуре, содержащей `Try...Catch...Finally` оператор.</span><span class="sxs-lookup"><span data-stu-id="b4093-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4093-122">Пример</span><span class="sxs-lookup"><span data-stu-id="b4093-122">Example</span></span>  

 <span data-ttu-id="b4093-123">В этом примере `Resume` оператор используется для завершения обработки ошибок в процедуре, а затем возобновляется выполнение с инструкцией, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="b4093-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="b4093-124">Номер ошибки 55 создается для демонстрации использования `Resume` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b4093-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="b4093-125">Требования</span><span class="sxs-lookup"><span data-stu-id="b4093-125">Requirements</span></span>  

 <span data-ttu-id="b4093-126">**Пространство имен:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="b4093-126">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="b4093-127">**Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="b4093-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4093-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b4093-128">See also</span></span>

- [<span data-ttu-id="b4093-129">Оператор Try…Catch…Finally</span><span class="sxs-lookup"><span data-stu-id="b4093-129">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="b4093-130">Оператор Error</span><span class="sxs-lookup"><span data-stu-id="b4093-130">Error Statement</span></span>](error-statement.md)
- [<span data-ttu-id="b4093-131">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="b4093-131">On Error Statement</span></span>](on-error-statement.md)
