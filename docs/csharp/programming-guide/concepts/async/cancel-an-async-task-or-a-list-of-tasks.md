---
title: Отмена асинхронной задачи или списка задач (C#)
description: Используйте эти примеры для добавления кнопки, которая отменяет асинхронное приложение до его завершения. Это приложение C# скачивает содержимое одного или нескольких веб-сайтов.
ms.date: 07/20/2015
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 21bdbc3bc7c3b752fab160429d71356fb87d9976
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925350"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-c"></a><span data-ttu-id="f23a6-104">Отмена асинхронной задачи или списка задач в C#</span><span class="sxs-lookup"><span data-stu-id="f23a6-104">Cancel an async task or a list of tasks (C#)</span></span>

<span data-ttu-id="f23a6-105">Вы можете настроить кнопку, которая позволит отменить асинхронное приложение в случае, если вы не захотите дожидаться его завершения.</span><span class="sxs-lookup"><span data-stu-id="f23a6-105">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="f23a6-106">Выполнив код в приведенных ниже примерах, вы сможете добавить в приложение кнопку отмены, загружающую содержимое одного веб-сайта или список веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="f23a6-106">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>

<span data-ttu-id="f23a6-107">В этих примерах используется пользовательский интерфейс, описанный в разделе [Настройка асинхронного приложения (C#)](./fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="f23a6-107">The examples use the UI that [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) describes.</span></span>

> [!NOTE]
> <span data-ttu-id="f23a6-108">Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="f23a6-108">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="cancel-a-task"></a><span data-ttu-id="f23a6-109">Отмена задачи</span><span class="sxs-lookup"><span data-stu-id="f23a6-109">Cancel a task</span></span>

<span data-ttu-id="f23a6-110">Код в первом примере связывает кнопку **Отмена** с отдельной задачей загрузки.</span><span class="sxs-lookup"><span data-stu-id="f23a6-110">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="f23a6-111">Если нажать эту кнопку, когда приложение загружает содержимое, загрузка будет отменена.</span><span class="sxs-lookup"><span data-stu-id="f23a6-111">If you choose the button while the application is downloading content, the download is canceled.</span></span>

### <a name="download-the-example"></a><span data-ttu-id="f23a6-112">Скачивание примера</span><span class="sxs-lookup"><span data-stu-id="f23a6-112">Download the example</span></span>

<span data-ttu-id="f23a6-113">Скачать полный проект Windows Presentation Foundation (WPF) можно со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea). Затем выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f23a6-113">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="f23a6-114">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f23a6-114">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="f23a6-115">В строке меню выберите **Файл** > **Открыть** > **Решение или проект**.</span><span class="sxs-lookup"><span data-stu-id="f23a6-115">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="f23a6-116">В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы распаковали, а затем откройте файл решения (SLN) для AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="f23a6-116">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="f23a6-117">В **обозревателе решений** откройте контекстное меню проекта **CancelATask** и выберите команду **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="f23a6-117">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="f23a6-118">Нажмите клавишу **F5**, чтобы запустить проект (или нажмите клавиши **Ctrl**+**F5**, чтобы запустить проект без отладки).</span><span class="sxs-lookup"><span data-stu-id="f23a6-118">Choose the **F5** key to run the project (or, press **Ctrl**+**F5** to run the project without debugging it).</span></span>

> [!TIP]
> <span data-ttu-id="f23a6-119">Если не хотите скачивать проект, можете просмотреть файл MainWindow.xaml.cs в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="f23a6-119">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>

### <a name="build-the-example"></a><span data-ttu-id="f23a6-120">Сборка примера</span><span class="sxs-lookup"><span data-stu-id="f23a6-120">Build the example</span></span>
 <span data-ttu-id="f23a6-121">Следующие изменения добавляют кнопку **Отмена** в приложение, загружающее веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="f23a6-121">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="f23a6-122">Если вы не хотите загружать или собирать пример, просмотрите конечный результат в разделе "Завершенные примеры" в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="f23a6-122">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="f23a6-123">Звездочками отмечены изменения в коде.</span><span class="sxs-lookup"><span data-stu-id="f23a6-123">Asterisks mark the changes in the code.</span></span>

 <span data-ttu-id="f23a6-124">Для самостоятельной сборки примера шаг за шагом выполните инструкции в разделе "Загрузка примера", но в качестве **запускаемого проекта** выберите проект **StarterCode**, а не **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="f23a6-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>

 <span data-ttu-id="f23a6-125">Внесите в файл MainWindow.xaml.cs проекта указанные ниже изменения.</span><span class="sxs-lookup"><span data-stu-id="f23a6-125">Then add the following changes to the MainWindow.xaml.cs file of that project.</span></span>

1. <span data-ttu-id="f23a6-126">Объявите переменную `CancellationTokenSource`, `cts`, которая находится в области действия всех методов, имеющих к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="f23a6-126">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>

    ```csharp
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. <span data-ttu-id="f23a6-127">Добавьте следующий обработчик событий для кнопки **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="f23a6-127">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="f23a6-128">Этот обработчик событий использует метод <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> для отправки уведомления в `cts` при запросе отмены пользователем.</span><span class="sxs-lookup"><span data-stu-id="f23a6-128">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>

    ```csharp
    // ***Add an event handler for the Cancel button.
    private void cancelButton_Click(object sender, RoutedEventArgs e)
    {
        if (cts != null)
        {
            cts.Cancel();
        }
    }
    ```

3. <span data-ttu-id="f23a6-129">Внесите в обработчик событий указанные ниже изменения для кнопки **Пуск**, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="f23a6-129">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>

    - <span data-ttu-id="f23a6-130">Создайте экземпляр `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="f23a6-130">Instantiate the `CancellationTokenSource`, `cts`.</span></span>

        ```csharp
        // ***Instantiate the CancellationTokenSource.
        cts = new CancellationTokenSource();
        ```

    - <span data-ttu-id="f23a6-131">В вызове `AccessTheWebAsync`, который скачивает содержимое заданного веб-сайта, отправьте свойство <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> объекта `cts` в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="f23a6-131">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="f23a6-132">Если запрашивается отмена, свойство `Token` распространяет сообщение.</span><span class="sxs-lookup"><span data-stu-id="f23a6-132">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="f23a6-133">Добавьте блок catch, который отображает сообщение в случае, если пользователь решает отменить операцию загрузки.</span><span class="sxs-lookup"><span data-stu-id="f23a6-133">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="f23a6-134">Эти изменения показаны в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="f23a6-134">The following code shows the changes.</span></span>

        ```csharp
        try
        {
            // ***Send a token to carry the message if cancellation is requested.
            int contentLength = await AccessTheWebAsync(cts.Token);
            resultsTextBox.Text += $"\r\nLength of the downloaded string: {contentLength}.\r\n";
        }
        // *** If cancellation is requested, an OperationCanceledException results.
        catch (OperationCanceledException)
        {
            resultsTextBox.Text += "\r\nDownload canceled.\r\n";
        }
        catch (Exception)
        {
            resultsTextBox.Text += "\r\nDownload failed.\r\n";
        }
        ```

4. <span data-ttu-id="f23a6-135">В `AccessTheWebAsync` используйте перегрузку <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> метода `GetAsync` в типе <xref:System.Net.Http.HttpClient> для скачивания содержимого веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="f23a6-135">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="f23a6-136">Передайте `ct` параметр <xref:System.Threading.CancellationToken> метода `AccessTheWebAsync` в качестве второго аргумента.</span><span class="sxs-lookup"><span data-stu-id="f23a6-136">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="f23a6-137">Благодаря токену, если пользователь нажмет кнопку **Отмена**, будет выведено соответствующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="f23a6-137">The token carries the message if the user chooses the **Cancel** button.</span></span>

     <span data-ttu-id="f23a6-138">Эти изменения в `AccessTheWebAsync` показаны в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="f23a6-138">The following code shows the changes in `AccessTheWebAsync`.</span></span>

    ```csharp
    // ***Provide a parameter for the CancellationToken.
    async Task<int> AccessTheWebAsync(CancellationToken ct)
    {
        HttpClient client = new HttpClient();

        resultsTextBox.Text += "\r\nReady to download.\r\n";

        // You might need to slow things down to have a chance to cancel.
        await Task.Delay(250);

        // GetAsync returns a Task<HttpResponseMessage>.
        // ***The ct argument carries the message if the Cancel button is chosen.
        HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // The result of the method is the length of the downloaded website.
        return urlContents.Length;
    }
    ```

5. <span data-ttu-id="f23a6-139">Если программа не отменяется, она выдает представленный ниже результат.</span><span class="sxs-lookup"><span data-stu-id="f23a6-139">If you don’t cancel the program, it produces the following output.</span></span>

    ```text
    Ready to download.
    Length of the downloaded string: 158125.
    ```

     <span data-ttu-id="f23a6-140">Если вы нажмете кнопку **Отмена**, прежде чем программа завершит загрузку содержимого, будет выдан представленный ниже результат.</span><span class="sxs-lookup"><span data-stu-id="f23a6-140">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>

    ```text
    Ready to download.
    Download canceled.
    ```

## <a name="cancel-a-list-of-tasks"></a><span data-ttu-id="f23a6-141">Отмена списка задач</span><span class="sxs-lookup"><span data-stu-id="f23a6-141">Cancel a list of tasks</span></span>

<span data-ttu-id="f23a6-142">Вы можете расширить предыдущий пример до отмены сразу нескольких задач, связав с каждой из них один и тот же экземпляр `CancellationTokenSource`.</span><span class="sxs-lookup"><span data-stu-id="f23a6-142">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="f23a6-143">В этом случае кнопка **Отмена** отменяет сразу все незавершенные задачи.</span><span class="sxs-lookup"><span data-stu-id="f23a6-143">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>

### <a name="download-the-example"></a><span data-ttu-id="f23a6-144">Скачивание примера</span><span class="sxs-lookup"><span data-stu-id="f23a6-144">Download the example</span></span>

<span data-ttu-id="f23a6-145">Скачать полный проект Windows Presentation Foundation (WPF) можно со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea). Затем выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f23a6-145">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="f23a6-146">Распакуйте загруженный файл, а затем запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f23a6-146">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="f23a6-147">В строке меню выберите **Файл** > **Открыть** > **Решение или проект**.</span><span class="sxs-lookup"><span data-stu-id="f23a6-147">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="f23a6-148">В диалоговом окне **Открытие проекта** откройте папку с примером кода, который вы распаковали, а затем откройте файл решения (SLN) для AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="f23a6-148">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="f23a6-149">В **обозревателе решений** откройте контекстное меню проекта **CancelAListOfTasks** и выберите команду **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="f23a6-149">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="f23a6-150">Нажмите клавишу **F5**, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="f23a6-150">Choose the **F5** key to run the project.</span></span>

     <span data-ttu-id="f23a6-151">Нажмите клавиши **CTRL**+**F5**, чтобы запустить проект без отладки.</span><span class="sxs-lookup"><span data-stu-id="f23a6-151">Choose the **Ctrl**+**F5** keys to run the project without debugging it.</span></span>

<span data-ttu-id="f23a6-152">Если не хотите скачивать проект, можете просмотреть файл MainWindow.xaml.cs в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="f23a6-152">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>

### <a name="build-the-example"></a><span data-ttu-id="f23a6-153">Сборка примера</span><span class="sxs-lookup"><span data-stu-id="f23a6-153">Build the example</span></span>

<span data-ttu-id="f23a6-154">Для самостоятельного построения примера шаг за шагом выполните инструкции в разделе "Загрузка примера", но выберите **CancelATask** как **запускаемый проект**.</span><span class="sxs-lookup"><span data-stu-id="f23a6-154">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="f23a6-155">Добавьте в проект указанные ниже изменения.</span><span class="sxs-lookup"><span data-stu-id="f23a6-155">Add the following changes to that project.</span></span> <span data-ttu-id="f23a6-156">Звездочками отмечены изменения в программе.</span><span class="sxs-lookup"><span data-stu-id="f23a6-156">Asterisks mark the changes in the program.</span></span>

1. <span data-ttu-id="f23a6-157">Добавьте метод для создания списка веб-адресов.</span><span class="sxs-lookup"><span data-stu-id="f23a6-157">Add a method to create a list of web addresses.</span></span>

    ```csharp
    // ***Add a method that creates a list of web addresses.
    private List<string> SetUpURLList()
    {
        List<string> urls = new List<string>
        {
            "https://msdn.microsoft.com",
            "https://msdn.microsoft.com/library/hh290138.aspx",
            "https://msdn.microsoft.com/library/hh290140.aspx",
            "https://msdn.microsoft.com/library/dd470362.aspx",
            "https://msdn.microsoft.com/library/aa578028.aspx",
            "https://msdn.microsoft.com/library/ms404677.aspx",
            "https://msdn.microsoft.com/library/ff730837.aspx"
        };
        return urls;
    }
    ```

2. <span data-ttu-id="f23a6-158">Вызовите метод в `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="f23a6-158">Call the method in `AccessTheWebAsync`.</span></span>

    ```csharp
    // ***Call SetUpURLList to make a list of web addresses.
    List<string> urlList = SetUpURLList();
    ```

3. <span data-ttu-id="f23a6-159">Добавьте в `AccessTheWebAsync` следующий цикл для обработки каждого веб-адреса в списке.</span><span class="sxs-lookup"><span data-stu-id="f23a6-159">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>

    ```csharp
    // ***Add a loop to process the list of web addresses.
    foreach (var url in urlList)
    {
        // GetAsync returns a Task<HttpResponseMessage>.
        // Argument ct carries the message if the Cancel button is chosen.
        // ***Note that the Cancel button can cancel all remaining downloads.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
    }
    ```

4. <span data-ttu-id="f23a6-160">Поскольку `AccessTheWebAsync` отображает длину, метод не должен ничего возвращать.</span><span class="sxs-lookup"><span data-stu-id="f23a6-160">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="f23a6-161">Удалите инструкцию return и измените тип возвращаемого значения на <xref:System.Threading.Tasks.Task> вместо <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="f23a6-161">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>

    ```csharp
    async Task AccessTheWebAsync(CancellationToken ct)
    ```

     <span data-ttu-id="f23a6-162">Вызовите метод из `startButton_Click`, используя не выражение, а оператор.</span><span class="sxs-lookup"><span data-stu-id="f23a6-162">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>

    ```csharp
    await AccessTheWebAsync(cts.Token);
    ```

5. <span data-ttu-id="f23a6-163">Если программа не отменяется, она выдает представленный ниже результат.</span><span class="sxs-lookup"><span data-stu-id="f23a6-163">If you don’t cancel the program, it produces the following output.</span></span>

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

     <span data-ttu-id="f23a6-164">При нажатии кнопки **Отмена** до завершения загрузки выходные данные будут включать объем данных, загруженных до отмены.</span><span class="sxs-lookup"><span data-stu-id="f23a6-164">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="complete-examples"></a><span data-ttu-id="f23a6-165">Полные примеры</span><span class="sxs-lookup"><span data-stu-id="f23a6-165">Complete examples</span></span>

<span data-ttu-id="f23a6-166">Следующие разделы содержат код каждого из приведенных выше примеров.</span><span class="sxs-lookup"><span data-stu-id="f23a6-166">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="f23a6-167">Обратите внимание на то, что необходимо добавить ссылку для <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="f23a6-167">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="f23a6-168">Вы можете скачать проект из статьи c [примером использования async. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="f23a6-168">You can download the projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

### <a name="example---cancel-a-task"></a><span data-ttu-id="f23a6-169">Пример отмены задачи</span><span class="sxs-lookup"><span data-stu-id="f23a6-169">Example - Cancel a task</span></span>

<span data-ttu-id="f23a6-170">Приведенный ниже код представляет собой полный файл MainWindow.xaml.cs, демонстрирующий отмену отдельной задачи.</span><span class="sxs-lookup"><span data-stu-id="f23a6-170">The following code is the complete MainWindow.xaml.cs file for the example that cancels a single task.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive for System.Threading.

using System.Threading;
namespace CancelATask
{
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // ***Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                // ***Send a token to carry the message if cancellation is requested.
                int contentLength = await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }
            // *** If cancellation is requested, an OperationCanceledException results.
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownload canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownload failed.\r\n";
            }

            // ***Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // ***Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // ***Provide a parameter for the CancellationToken.
        async Task<int> AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            resultsTextBox.Text += "\r\nReady to download.\r\n";

            // You might need to slow things down to have a chance to cancel.
            await Task.Delay(250);

            // GetAsync returns a Task<HttpResponseMessage>.
            // ***The ct argument carries the message if the Cancel button is chosen.
            HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            // The result of the method is the length of the downloaded website.
            return urlContents.Length;
        }
    }

    // Output for a successful download:

    // Ready to download.

    // Length of the downloaded string: 158125.

    // Or, if you cancel:

    // Ready to download.

    // Download canceled.
}
```

### <a name="example---cancel-a-list-of-tasks"></a><span data-ttu-id="f23a6-171">Примеры отмены списка задач</span><span class="sxs-lookup"><span data-stu-id="f23a6-171">Example - Cancel a list of tasks</span></span>

<span data-ttu-id="f23a6-172">Приведенный ниже код представляет собой полный файл MainWindow.xaml.cs, демонстрирующий отмену списка задач.</span><span class="sxs-lookup"><span data-stu-id="f23a6-172">The following code is the complete MainWindow.xaml.cs file for the example that cancels a list of tasks.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive for System.Threading.
using System.Threading;

namespace CancelAListOfTasks
{
    public partial class MainWindow : Window
    {
        // Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                await AccessTheWebAsync(cts.Token);
                // ***Small change in the display lines.
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.";
            }

            // Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // Provide a parameter for the CancellationToken.
        // ***Change the return type to Task because the method has no return statement.
        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // ***Call SetUpURLList to make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Add a loop to process the list of web addresses.
            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // ***Note that the Cancel button can cancel all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        // ***Add a method that creates a list of web addresses.
        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Output if you do not choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Length of the downloaded string: 158124.

    //Length of the downloaded string: 204890.

    //Length of the downloaded string: 175488.

    //Length of the downloaded string: 145790.

    //Downloads complete.

    // Sample output if you choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Downloads canceled.
}
```

## <a name="see-also"></a><span data-ttu-id="f23a6-173">См. также</span><span class="sxs-lookup"><span data-stu-id="f23a6-173">See also</span></span>

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [<span data-ttu-id="f23a6-174">Асинхронное программирование с использованием ключевых слов async и await (C#)</span><span class="sxs-lookup"><span data-stu-id="f23a6-174">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- <span data-ttu-id="f23a6-175">[Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) (Тонкая настройка асинхронного приложения в C#)</span><span class="sxs-lookup"><span data-stu-id="f23a6-175">[Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md)</span></span>
- [<span data-ttu-id="f23a6-176">Пример использования Async. Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="f23a6-176">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
