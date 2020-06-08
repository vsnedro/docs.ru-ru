---
title: Устранение неполадок, связанных с прослушивателями журнала
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 8d2d8294d9e9bb42d72fe4f6c37bf846bd644907
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398322"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="b215f-102">Устранение неполадок, связанных с прослушивателями журнала (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b215f-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="b215f-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.</span><span class="sxs-lookup"><span data-stu-id="b215f-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="b215f-104">Чтобы определить, какие прослушиватели журналов получают эти сообщения, см. раздел [Пошаговое руководство. Определение места записи информации для My.Application.Log](walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="b215f-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="b215f-105">Объект `Log` может использовать фильтрацию журнала для ограничения объема данных, регистрируемых в журнале.</span><span class="sxs-lookup"><span data-stu-id="b215f-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="b215f-106">Если фильтры настроены неправильно, журналы могут содержать неверные данные.</span><span class="sxs-lookup"><span data-stu-id="b215f-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="b215f-107">Дополнительные сведения см. в разделе [Пошаговое руководство. Фильтрация вывода My.Application.Log](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="b215f-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="b215f-108">Однако если журнал настроен неправильно, необходима дополнительная информация о его текущей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b215f-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="b215f-109">Эту информацию можно получить с помощью расширенного свойства журнала `TraceSource`.</span><span class="sxs-lookup"><span data-stu-id="b215f-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="b215f-110">Определение прослушивателей журнала для объекта Log в коде</span><span class="sxs-lookup"><span data-stu-id="b215f-110">To determine the log listeners for the Log object in code</span></span>  
  
1. <span data-ttu-id="b215f-111">Импортируйте пространство имен <xref:System.Diagnostics> в начало файла кода.</span><span class="sxs-lookup"><span data-stu-id="b215f-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="b215f-112">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="b215f-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. <span data-ttu-id="b215f-113">Создайте функцию, которая возвращает строку, состоящую из информации о каждом из прослушивателей журнала.</span><span class="sxs-lookup"><span data-stu-id="b215f-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. <span data-ttu-id="b215f-114">Передайте коллекцию прослушивателей журнала трассировки в функцию `GetListeners` и отобразите возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="b215f-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     <span data-ttu-id="b215f-115">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="b215f-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b215f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b215f-116">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="b215f-117">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="b215f-117">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="b215f-118">Пошаговое руководство. Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="b215f-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
