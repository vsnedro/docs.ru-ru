---
title: Прослушиватели трассировки
description: Изучите прослушиватели трассировки, которые являются механизмом сбора и записи сообщений трассировки, отправленных в .NET. Прослушиватель собирает, хранит и маршрутизирует сообщения.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Listener object types
- listeners
- Trace class, listeners
- trace listeners, about trace listeners
- Listeners collection
- trace listeners
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
ms.openlocfilehash: 8cd79d21d66d23f834b7ef0012d8360884028ac6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238123"
---
# <a name="trace-listeners"></a><span data-ttu-id="fa405-104">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="fa405-104">Trace Listeners</span></span>

<span data-ttu-id="fa405-105">При использовании классов **Trace**, **Debug** и <xref:System.Diagnostics.TraceSource> необходимо обеспечить механизм сбора и записи отправляемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="fa405-105">When using **Trace**, **Debug** and <xref:System.Diagnostics.TraceSource>, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="fa405-106">Сообщения трассировки получаются *прослушивателями*.</span><span class="sxs-lookup"><span data-stu-id="fa405-106">Trace messages are received by *listeners*.</span></span> <span data-ttu-id="fa405-107">В задачу прослушивателя входит сбор, хранение и маршрутизация сообщений трассировки.</span><span class="sxs-lookup"><span data-stu-id="fa405-107">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="fa405-108">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту, например, в журнал событий, окно или текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fa405-108">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="fa405-109">Прослушиватели доступны для классов **Debug**, **Trace** и <xref:System.Diagnostics.TraceSource>, каждый из которых может отправлять свои выходные данные разным объектам прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="fa405-109">Listeners are available to the **Debug**, **Trace**, and <xref:System.Diagnostics.TraceSource> classes, each of which can send its output to a variety of listener objects.</span></span> <span data-ttu-id="fa405-110">Ниже перечислены часто используемые предварительно определенные прослушиватели.</span><span class="sxs-lookup"><span data-stu-id="fa405-110">The following are the commonly used predefined listeners:</span></span>  
  
- <span data-ttu-id="fa405-111">Прослушиватель <xref:System.Diagnostics.TextWriterTraceListener> перенаправляет выходные данные в экземпляр класса <xref:System.IO.TextWriter> или любой объект, являющийся классом <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="fa405-111">A <xref:System.Diagnostics.TextWriterTraceListener> redirects output to an instance of the <xref:System.IO.TextWriter> class or to anything that is a <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="fa405-112">Он также может осуществлять запись в консоль или файл, потому что это классы <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="fa405-112">It can also write to the console or to a file, because these are <xref:System.IO.Stream> classes.</span></span>  
  
- <span data-ttu-id="fa405-113">Класс <xref:System.Diagnostics.EventLogTraceListener> перенаправляет выходные данные в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="fa405-113">An <xref:System.Diagnostics.EventLogTraceListener> redirects output to an event log.</span></span>  
  
- <span data-ttu-id="fa405-114">Класс <xref:System.Diagnostics.DefaultTraceListener> выводит сообщения методов **Write** и **WriteLine** в строку **OutputDebugString** и метод **Debugger.Log**.</span><span class="sxs-lookup"><span data-stu-id="fa405-114">A <xref:System.Diagnostics.DefaultTraceListener> emits **Write** and **WriteLine** messages to the **OutputDebugString** and to the **Debugger.Log** method.</span></span> <span data-ttu-id="fa405-115">В Visual Studio в этом случае сообщения отладки отображаются в окне «Вывод».</span><span class="sxs-lookup"><span data-stu-id="fa405-115">In Visual Studio, this causes the debugging messages to appear in the Output window.</span></span> <span data-ttu-id="fa405-116">Сообщения метода **Fail** и завершившегося сбоем метода **Assert** также выводятся в API Windows **OutputDebugString** и методе **Debugger.Log**. Также в этом случае отображается поле сообщений.</span><span class="sxs-lookup"><span data-stu-id="fa405-116">**Fail** and failed **Assert** messages also emit to the **OutputDebugString** Windows API and the **Debugger.Log** method, and also cause a message box to be displayed.</span></span> <span data-ttu-id="fa405-117">Данное поведение — это поведение по умолчанию для сообщений **Debug** и **Trace**, так как прослушиватель **DefaultTraceListener** автоматически включается в каждую коллекцию `Listeners` и является единственным автоматически включаемым прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="fa405-117">This behavior is the default behavior for **Debug** and **Trace** messages, because **DefaultTraceListener** is automatically included in every `Listeners` collection and is the only listener automatically included.</span></span>  
  
- <span data-ttu-id="fa405-118">Объект <xref:System.Diagnostics.ConsoleTraceListener> направляет выходные данные трассировки или отладки в стандартный вывод или стандартный поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="fa405-118">A <xref:System.Diagnostics.ConsoleTraceListener> directs tracing or debugging output to either the standard output or the standard error stream.</span></span>  
  
- <span data-ttu-id="fa405-119">Прослушиватель <xref:System.Diagnostics.DelimitedListTraceListener> направляет выходные данные трассировки или отладки в модуль записи текста, например модуль записи в поток, или в поток, например файловый поток.</span><span class="sxs-lookup"><span data-stu-id="fa405-119">A <xref:System.Diagnostics.DelimitedListTraceListener> directs tracing or debugging output to a text writer, such as a stream writer, or to a stream, such as a file stream.</span></span> <span data-ttu-id="fa405-120">Выходные данные трассировки имеют текстовый формат с разделителями, в котором используется разделитель, заданный <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> свойством.</span><span class="sxs-lookup"><span data-stu-id="fa405-120">The trace output is in a delimited text format that uses the delimiter specified by the <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> property.</span></span>  
  
- <span data-ttu-id="fa405-121">Прослушиватель <xref:System.Diagnostics.XmlWriterTraceListener> направляет вывод отладки или трассировки в качестве кодированных в XML данных в метод <xref:System.IO.TextWriter> или поток <xref:System.IO.Stream>, например <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="fa405-121">An <xref:System.Diagnostics.XmlWriterTraceListener> directs tracing or debugging output as XML-encoded data to a <xref:System.IO.TextWriter> or to a <xref:System.IO.Stream>, such as a <xref:System.IO.FileStream>.</span></span>  
  
 <span data-ttu-id="fa405-122">Если нужно, чтобы какой-либо еще прослушиватель, помимо <xref:System.Diagnostics.DefaultTraceListener>, получал выходные данные **Debug**, **Trace** и <xref:System.Diagnostics.TraceSource>, необходимо добавить его в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="fa405-122">If you want any listener besides the <xref:System.Diagnostics.DefaultTraceListener> to receive **Debug**, **Trace** and <xref:System.Diagnostics.TraceSource> output, you must add it to the `Listeners` collection.</span></span> <span data-ttu-id="fa405-123">Дополнительные сведения см. в разделе [Практическое руководство. Создание и инициализация прослушивателей трассировки](how-to-create-and-initialize-trace-listeners.md) и [Практическое руководство. Использование TraceSource и фильтров с прослушивателями трассировки](how-to-use-tracesource-and-filters-with-trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="fa405-123">For more information, see [How to: Create and Initialize Trace Listeners](how-to-create-and-initialize-trace-listeners.md) and [How to: Use TraceSource and Filters with Trace Listeners](how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span> <span data-ttu-id="fa405-124">Любой прослушиватель из коллекции **Listeners** получает те же сообщения от методов вывода трассировки.</span><span class="sxs-lookup"><span data-stu-id="fa405-124">Any listener in the **Listeners** collection gets the same messages from the trace output methods.</span></span> <span data-ttu-id="fa405-125">Предположим, например, что настроены два прослушивателя: **TextWriterTraceListener** и **EventLogTraceListener**.</span><span class="sxs-lookup"><span data-stu-id="fa405-125">For example, suppose you set up two listeners: a **TextWriterTraceListener** and an **EventLogTraceListener**.</span></span> <span data-ttu-id="fa405-126">Каждый прослушиватель получает одно и то же сообщение.</span><span class="sxs-lookup"><span data-stu-id="fa405-126">Each listener receives the same message.</span></span> <span data-ttu-id="fa405-127">Прослушиватель **TextWriterTraceListener** направляет выходные данные в поток, а **EventLogTraceListener** направляет выходные данные в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="fa405-127">The **TextWriterTraceListener** would direct its output to a stream, and the **EventLogTraceListener** would direct its output to an event log.</span></span>  
  
 <span data-ttu-id="fa405-128">В приведенном ниже примере показана отправка выходных данных в коллекцию **прослушивателей**.</span><span class="sxs-lookup"><span data-stu-id="fa405-128">The following example shows how to send output to the **Listeners** collection.</span></span>  
  
```vb  
' Use this example when debugging.  
Debug.WriteLine("Error in Widget 42")  
' Use this example when tracing.  
Trace.WriteLine("Error in Widget 42")  
```  
  
```csharp  
// Use this example when debugging.  
System.Diagnostics.Debug.WriteLine("Error in Widget 42");  
// Use this example when tracing.  
System.Diagnostics.Trace.WriteLine("Error in Widget 42");  
```  
  
 <span data-ttu-id="fa405-129">При отладке и трассировке используется одна и та же коллекция **прослушивателей**, поэтому если добавить объект прослушивателя в коллекцию **Debug.Listeners** в приложении, он также будет добавлен и в коллекцию **Trace.Listeners**.</span><span class="sxs-lookup"><span data-stu-id="fa405-129">Debug and trace share the same **Listeners** collection, so if you add a listener object to a **Debug.Listeners** collection in your application, it gets added to the **Trace.Listeners** collection as well.</span></span>  
  
 <span data-ttu-id="fa405-130">В следующем примере показано использование прослушивателя для отправки сведений трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="fa405-130">The following example shows how to use a listener to send tracing information to a console:</span></span>  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a><span data-ttu-id="fa405-131">Прослушиватели, определяемые разработчиками</span><span class="sxs-lookup"><span data-stu-id="fa405-131">Developer-Defined Listeners</span></span>  

 <span data-ttu-id="fa405-132">Можно определить собственные прослушиватели путем наследования от базового класса **TraceListener** и переопределения его методов своими пользовательскими методами.</span><span class="sxs-lookup"><span data-stu-id="fa405-132">You can define your own listeners by inheriting from the **TraceListener** base class and overriding its methods with your customized methods.</span></span> <span data-ttu-id="fa405-133">Дополнительные сведения о создании прослушивателей, определяемых разработчиками, см. в описании <xref:System.Diagnostics.TraceListener> в справочнике по .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa405-133">For more information on creating developer-defined listeners, see <xref:System.Diagnostics.TraceListener> in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa405-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fa405-134">See also</span></span>

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="fa405-135">Трассировка и инструментирование приложений</span><span class="sxs-lookup"><span data-stu-id="fa405-135">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="fa405-136">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="fa405-136">Trace Switches</span></span>](trace-switches.md)
