---
title: Практическое руководство. Запись в журнал сведений об исключениях
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: 59ed7b836126a38f32b7c6f479570a566d236e6c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410118"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="8f57f-102">Практическое руководство. Запись в журнал сведений об исключениях в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f57f-102">How to: Log Exceptions in Visual Basic</span></span>

<span data-ttu-id="8f57f-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал сведений об исключениях, возникающих в приложении.</span><span class="sxs-lookup"><span data-stu-id="8f57f-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="8f57f-104">Эти примеры демонстрируют применение метода `My.Application.Log.WriteException` для регистрации явно перехваченных исключений и исключений, которые не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="8f57f-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="8f57f-105">Для записи сведений в журнал используйте метод `My.Application.Log.WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="8f57f-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="8f57f-106">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f57f-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="8f57f-107">Запись обработанного исключения в журнал</span><span class="sxs-lookup"><span data-stu-id="8f57f-107">To log a handled exception</span></span>  
  
1. <span data-ttu-id="8f57f-108">Создайте метод, который будет генерировать сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="8f57f-108">Create the method that will generate the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#9)]  
  
2. <span data-ttu-id="8f57f-109">Воспользуйтесь блоком `Try...Catch` для перехвата исключения.</span><span class="sxs-lookup"><span data-stu-id="8f57f-109">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#6)]  
  
3. <span data-ttu-id="8f57f-110">Поместите код, который может генерировать исключение, в блок `Try`.</span><span class="sxs-lookup"><span data-stu-id="8f57f-110">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="8f57f-111">Раскомментируйте строки `Dim` и `MsgBox`, чтобы вызвать исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="8f57f-111">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#7)]  
  
4. <span data-ttu-id="8f57f-112">В блоке `Catch` для записи сведений об исключении используйте метод `My.Application.Log.WriteException`.</span><span class="sxs-lookup"><span data-stu-id="8f57f-112">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#8)]  
  
     <span data-ttu-id="8f57f-113">В следующем примере показан полный код для записи обработанного исключения в журнал.</span><span class="sxs-lookup"><span data-stu-id="8f57f-113">The following example shows the complete code for logging a handled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#10)]  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="8f57f-114">Запись необработанного исключения в журнал</span><span class="sxs-lookup"><span data-stu-id="8f57f-114">To log an unhandled exception</span></span>  
  
1. <span data-ttu-id="8f57f-115">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="8f57f-115">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8f57f-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8f57f-116">On the **Project** menu, choose **Properties**.</span></span>  
  
2. <span data-ttu-id="8f57f-117">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="8f57f-117">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="8f57f-118">Нажмите кнопку **Просмотреть события приложения** , чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="8f57f-118">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="8f57f-119">Откроется файл ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="8f57f-119">This opens the ApplicationEvents.vb file.</span></span>  
  
4. <span data-ttu-id="8f57f-120">Откройте в редакторе кода файл ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="8f57f-120">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="8f57f-121">В меню **Общие** выберите пункт **События MyApplication**.</span><span class="sxs-lookup"><span data-stu-id="8f57f-121">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5. <span data-ttu-id="8f57f-122">В меню **Объявления** выберите пункт **UnhandledException**.</span><span class="sxs-lookup"><span data-stu-id="8f57f-122">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="8f57f-123">Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> до запуска главного приложения.</span><span class="sxs-lookup"><span data-stu-id="8f57f-123">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6. <span data-ttu-id="8f57f-124">Добавьте метод `My.Application.Log.WriteException` в обработчик событий `UnhandledException` .</span><span class="sxs-lookup"><span data-stu-id="8f57f-124">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#4)]  
  
     <span data-ttu-id="8f57f-125">В следующем примере показан полный код для записи необработанного исключения в журнал.</span><span class="sxs-lookup"><span data-stu-id="8f57f-125">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="8f57f-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8f57f-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="8f57f-127">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="8f57f-127">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="8f57f-128">Практическое руководство. Запись сообщений в журнал</span><span class="sxs-lookup"><span data-stu-id="8f57f-128">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)
- [<span data-ttu-id="8f57f-129">Пошаговое руководство. Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="8f57f-129">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="8f57f-130">Пошаговое руководство. Изменение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="8f57f-130">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
