---
title: Практическое руководство. Отображение ошибок проверки в отдельно размещенном конструкторе
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: ccdb8941f46683dd1fd12387c0c5db2abe1d8dec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280043"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="b3555-102">Практическое руководство. Отображение ошибок проверки в отдельно размещенном конструкторе</span><span class="sxs-lookup"><span data-stu-id="b3555-102">How to: Display Validation Errors in a Rehosted Designer</span></span>

<span data-ttu-id="b3555-103">В этом разделе описывается получение и публикация ошибок проверки в переразмещенной конструктор рабочих процессов Windows.</span><span class="sxs-lookup"><span data-stu-id="b3555-103">This topic describes how to retrieve and publish validation errors in a rehosted Windows Workflow Designer.</span></span> <span data-ttu-id="b3555-104">Это предоставляет процедуру подтверждения того, что рабочий процесс в повторно размещенном конструкторе является допустимым.</span><span class="sxs-lookup"><span data-stu-id="b3555-104">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="b3555-105">Эта задача имеет две части.</span><span class="sxs-lookup"><span data-stu-id="b3555-105">This task has two parts.</span></span> <span data-ttu-id="b3555-106">Первой задачей является предоставление реализации <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span><span class="sxs-lookup"><span data-stu-id="b3555-106">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="b3555-107">Имеется один очень важный метод, реализуемый в этом интерфейсе, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>, который передает список объектов <xref:System.Activities.Presentation.Validation.ValidationErrorInfo>, содержащих сведения об ошибках, в журнал отладки.</span><span class="sxs-lookup"><span data-stu-id="b3555-107">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="b3555-108">После реализации интерфейса сведения об ошибках получаются путем публикации экземпляра этой реализации в контексте редактирования.</span><span class="sxs-lookup"><span data-stu-id="b3555-108">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="b3555-109">Реализация интерфейса IValidationErrorService</span><span class="sxs-lookup"><span data-stu-id="b3555-109">Implement the IValidationErrorService Interface</span></span>  
  
1. <span data-ttu-id="b3555-110">Здесь приводится образец кода для простой реализации, которая записывает ошибки проверки в журнал отладки.</span><span class="sxs-lookup"><span data-stu-id="b3555-110">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
    ```csharp  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine($"Error: {vei.Message}"));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="b3555-111">Публикация в контексте редактирования</span><span class="sxs-lookup"><span data-stu-id="b3555-111">Publishing to the Editing Context</span></span>  
  
1. <span data-ttu-id="b3555-112">Здесь приводится код, который публикует это в контексте редактирования.</span><span class="sxs-lookup"><span data-stu-id="b3555-112">Here is the code that will publish this to the editing context.</span></span>  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
