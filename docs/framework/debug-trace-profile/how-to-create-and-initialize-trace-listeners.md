---
title: Практическое руководство. Создание и инициализация прослушивателей трассировки
description: Узнайте, как создавать и инициализировать прослушиватели трассировки с помощью таких классов, как System. Diagnostics. DefaultTraceListener в .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- initializing trace listeners
- trace listeners, creating
- trace listeners, initializing
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 21726de1-61ee-4fdc-9dd0-3be49324d066
ms.openlocfilehash: 752306124e41a7fb7458daccc8c2891631eb9616
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051211"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="14b85-103">Практическое руководство. Создание и инициализация прослушивателей трассировки</span><span class="sxs-lookup"><span data-stu-id="14b85-103">How to: Create and Initialize Trace Listeners</span></span>

<span data-ttu-id="14b85-104">Классы <xref:System.Diagnostics.Debug?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace?displayProperty=nameWithType> отправляют сообщения объектам, которые называются прослушивателями. Эти объекты получают и обрабатывают эти сообщения.</span><span class="sxs-lookup"><span data-stu-id="14b85-104">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="14b85-105">Один из таких прослушивателей, <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, автоматически создается и инициализируется при включении трассировки или отладки.</span><span class="sxs-lookup"><span data-stu-id="14b85-105">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="14b85-106">Если требуется направить выходные данные типа <xref:System.Diagnostics.Trace> или <xref:System.Diagnostics.Debug> каким-либо дополнительным источникам, необходимо создать и инициализировать дополнительные прослушиватели трассировки.</span><span class="sxs-lookup"><span data-stu-id="14b85-106">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>

<span data-ttu-id="14b85-107">Создаваемые прослушиватели должны соответствовать индивидуальным требованиям приложения.</span><span class="sxs-lookup"><span data-stu-id="14b85-107">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="14b85-108">Например, если требуется текстовая запись всех выходных данных трассировки, создайте прослушиватель <xref:System.Diagnostics.TextWriterTraceListener>, который будет записывать все выходные данные в новый текстовый файл, если эта функция включена.</span><span class="sxs-lookup"><span data-stu-id="14b85-108">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="14b85-109">С другой стороны, если требуется просмотреть выходные данные только во время исполнения приложения, создайте прослушиватель <xref:System.Diagnostics.ConsoleTraceListener>, направляющий все выходные данные в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="14b85-109">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="14b85-110">Прослушиватель <xref:System.Diagnostics.EventLogTraceListener> может направлять выходные данные трассировки в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="14b85-110">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="14b85-111">Дополнительные сведения см. в разделе [прослушиватели трассировки](trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="14b85-111">For more information, see [Trace Listeners](trace-listeners.md).</span></span>

<span data-ttu-id="14b85-112">Можно создать прослушиватели трассировки в [файле конфигурации приложения](../configure-apps/index.md) или в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="14b85-112">You can create trace listeners in an [application configuration file](../configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="14b85-113">Рекомендуется использовать файлы конфигурации приложения, так как они позволяют добавлять, изменять или удалять прослушиватели трассировки без внесения изменений в код.</span><span class="sxs-lookup"><span data-stu-id="14b85-113">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="14b85-114">Создание и использование прослушивателя трассировки с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="14b85-114">To create and use a trace listener by using a configuration file</span></span>

1. <span data-ttu-id="14b85-115">Объявите прослушиватель трассировки в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="14b85-115">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="14b85-116">Если создаваемый прослушиватель требует какие-либо другие объекты, также объявите их.</span><span class="sxs-lookup"><span data-stu-id="14b85-116">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="14b85-117">В следующем примере показано создание прослушивателя с именем `myListener`, записывающего данные в текстовый файл `TextWriterOutput.log`.</span><span class="sxs-lookup"><span data-stu-id="14b85-117">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>

    ```xml
    <configuration>
      <system.diagnostics>
        <trace autoflush="false" indentsize="4">
          <listeners>
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="TextWriterOutput.log" />
            <remove name="Default" />
          </listeners>
        </trace>
      </system.diagnostics>
    </configuration>
    ```

2. <span data-ttu-id="14b85-118">Используйте класс <xref:System.Diagnostics.Trace> в своем коде для записи сообщения в прослушиватели трассировки.</span><span class="sxs-lookup"><span data-stu-id="14b85-118">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>

    ```vb
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="14b85-119">Создание и использование прослушивателя трассировки в коде</span><span class="sxs-lookup"><span data-stu-id="14b85-119">To create and use a trace listener in code</span></span>

- <span data-ttu-id="14b85-120">Добавьте прослушиватель трассировки в коллекцию <xref:System.Diagnostics.Trace.Listeners%2A> и отправьте сведения трассировки прослушивателям.</span><span class="sxs-lookup"><span data-stu-id="14b85-120">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>

    ```vb
    Trace.Listeners.Add(New TextWriterTraceListener("TextWriterOutput.log", "myListener"))
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.Listeners.Add(new TextWriterTraceListener("TextWriterOutput.log", "myListener"));
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

    <span data-ttu-id="14b85-121">\- или -</span><span class="sxs-lookup"><span data-stu-id="14b85-121">\- or -</span></span>

- <span data-ttu-id="14b85-122">Если не нужно, чтобы прослушиватель получал выходные данные трассировки, не добавляйте его в коллекцию <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="14b85-122">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="14b85-123">Допускается выдача выходных данных через прослушиватель независимо от коллекции <xref:System.Diagnostics.Trace.Listeners%2A> путем вызова собственных методов вывода прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="14b85-123">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="14b85-124">В следующем примере показано, как выполнить запись строки в прослушиватель, не являющийся частью коллекции <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="14b85-124">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>

    ```vb
    Dim myListener As New TextWriterTraceListener("TextWriterOutput.log", "myListener")
    myListener.WriteLine("Test message.")
    ' You must close or flush the trace listener to empty the output buffer.
    myListener.Flush()
    ```

    ```csharp
    TextWriterTraceListener myListener = new TextWriterTraceListener("TextWriterOutput.log", "myListener");
    myListener.WriteLine("Test message.");
    // You must close or flush the trace listener to empty the output buffer.
    myListener.Flush();
    ```

## <a name="see-also"></a><span data-ttu-id="14b85-125">См. также</span><span class="sxs-lookup"><span data-stu-id="14b85-125">See also</span></span>

- [<span data-ttu-id="14b85-126">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="14b85-126">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="14b85-127">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="14b85-127">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="14b85-128">Практическое руководство. Добавление операторов трассировки в код приложения</span><span class="sxs-lookup"><span data-stu-id="14b85-128">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="14b85-129">Трассировка и инструментирование приложений</span><span class="sxs-lookup"><span data-stu-id="14b85-129">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
