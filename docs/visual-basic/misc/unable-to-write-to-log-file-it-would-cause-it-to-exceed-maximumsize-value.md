---
title: Невозможно произвести запись в файл журнала, так как это приведет к превышению значения MaximumSize.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 95a7b9036e7c1494cd44c250b0580bab5144417b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059461"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="f61f2-102">Невозможно произвести запись в файл журнала, так как это приведет к превышению значения MaximumSize.</span><span class="sxs-lookup"><span data-stu-id="f61f2-102">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>

<span data-ttu-id="f61f2-103">Класс <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> не может выполнить запись в файл журнала, так как:</span><span class="sxs-lookup"><span data-stu-id="f61f2-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
- <span data-ttu-id="f61f2-104">размер файла журнала (в байтах) больше, чем значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A></span><span class="sxs-lookup"><span data-stu-id="f61f2-104">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="f61f2-105">—и—</span><span class="sxs-lookup"><span data-stu-id="f61f2-105">—and—</span></span>  
  
- <span data-ttu-id="f61f2-106">значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> равно <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span><span class="sxs-lookup"><span data-stu-id="f61f2-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f61f2-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f61f2-107">To correct this error</span></span>  
  
1. <span data-ttu-id="f61f2-108">Архивируйте существующие журналы и удалите их с компьютера, чтобы разрешить объекту <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> создавать новые журналы.</span><span class="sxs-lookup"><span data-stu-id="f61f2-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="f61f2-109">Измените значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> , чтобы разрешить журналы больших размеров.</span><span class="sxs-lookup"><span data-stu-id="f61f2-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3. <span data-ttu-id="f61f2-110">Задайте для свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> значение <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> , чтобы отменить сообщения без предупреждения, если журнал окажется слишком большим.</span><span class="sxs-lookup"><span data-stu-id="f61f2-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f61f2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f61f2-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="f61f2-112">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="f61f2-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="f61f2-113">My. Application. info. DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="f61f2-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
