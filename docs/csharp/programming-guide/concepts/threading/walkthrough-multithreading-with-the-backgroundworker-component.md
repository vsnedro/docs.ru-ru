---
title: "Пошаговое руководство. Многопоточность с помощью компонента BackgroundWorker (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 541a1ec788c337eea9965b8a46155e5c6606ea2f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a><span data-ttu-id="a5fda-102">Пошаговое руководство. Многопоточность с помощью компонента BackgroundWorker (C#)</span><span class="sxs-lookup"><span data-stu-id="a5fda-102">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>
<span data-ttu-id="a5fda-103">В этом пошаговом руководстве описывается создание многопоточного приложения Windows Forms, которое выполняет поиск заданного слова в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="a5fda-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="a5fda-104">В нем демонстрируются:</span><span class="sxs-lookup"><span data-stu-id="a5fda-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="a5fda-105">Определение класса с методом, который может вызываться компонентом <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="a5fda-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="a5fda-106">Обработка событий, вызываемых компонентом <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="a5fda-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="a5fda-107">Запуск компонента <xref:System.ComponentModel.BackgroundWorker> для выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="a5fda-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="a5fda-108">Реализация кнопки `Cancel`, которая останавливает компонент <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="a5fda-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="a5fda-109">Создание пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="a5fda-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="a5fda-110">Откройте новый проект приложения Windows Forms C# и создайте форму с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="a5fda-110">Open a new C# Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="a5fda-111">Добавьте две кнопки и четыре текстовых поля в `Form1`.</span><span class="sxs-lookup"><span data-stu-id="a5fda-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="a5fda-112">Присвойте им имена, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a5fda-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a5fda-113">Объект</span><span class="sxs-lookup"><span data-stu-id="a5fda-113">Object</span></span>|<span data-ttu-id="a5fda-114">Свойство</span><span class="sxs-lookup"><span data-stu-id="a5fda-114">Property</span></span>|<span data-ttu-id="a5fda-115">Параметр</span><span class="sxs-lookup"><span data-stu-id="a5fda-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="a5fda-116">Первая кнопка</span><span class="sxs-lookup"><span data-stu-id="a5fda-116">First button</span></span>|<span data-ttu-id="a5fda-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a5fda-117">`Name`, `Text`</span></span>|<span data-ttu-id="a5fda-118">Пуск, Пуск</span><span class="sxs-lookup"><span data-stu-id="a5fda-118">Start, Start</span></span>|  
    |<span data-ttu-id="a5fda-119">Вторая кнопка</span><span class="sxs-lookup"><span data-stu-id="a5fda-119">Second button</span></span>|<span data-ttu-id="a5fda-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a5fda-120">`Name`, `Text`</span></span>|<span data-ttu-id="a5fda-121">Отмена, Отмена</span><span class="sxs-lookup"><span data-stu-id="a5fda-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="a5fda-122">Первое текстовое поле</span><span class="sxs-lookup"><span data-stu-id="a5fda-122">First text box</span></span>|<span data-ttu-id="a5fda-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a5fda-123">`Name`, `Text`</span></span>|<span data-ttu-id="a5fda-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="a5fda-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="a5fda-125">Второе текстовое поле</span><span class="sxs-lookup"><span data-stu-id="a5fda-125">Second text box</span></span>|<span data-ttu-id="a5fda-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a5fda-126">`Name`, `Text`</span></span>|<span data-ttu-id="a5fda-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="a5fda-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="a5fda-128">Третье текстовое поле</span><span class="sxs-lookup"><span data-stu-id="a5fda-128">Third text box</span></span>|<span data-ttu-id="a5fda-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a5fda-129">`Name`, `Text`</span></span>|<span data-ttu-id="a5fda-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="a5fda-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="a5fda-131">Четвертое текстовое поле</span><span class="sxs-lookup"><span data-stu-id="a5fda-131">Fourth text box</span></span>|<span data-ttu-id="a5fda-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a5fda-132">`Name`, `Text`</span></span>|<span data-ttu-id="a5fda-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="a5fda-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="a5fda-134">Добавьте метку рядом с каждым текстовым полем.</span><span class="sxs-lookup"><span data-stu-id="a5fda-134">Add a label next to each text box.</span></span> <span data-ttu-id="a5fda-135">Задайте свойство `Text` для каждой метки, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a5fda-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a5fda-136">Объект</span><span class="sxs-lookup"><span data-stu-id="a5fda-136">Object</span></span>|<span data-ttu-id="a5fda-137">Свойство</span><span class="sxs-lookup"><span data-stu-id="a5fda-137">Property</span></span>|<span data-ttu-id="a5fda-138">Параметр</span><span class="sxs-lookup"><span data-stu-id="a5fda-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="a5fda-139">Первая метка</span><span class="sxs-lookup"><span data-stu-id="a5fda-139">First label</span></span>|`Text`|<span data-ttu-id="a5fda-140">Исходный файл</span><span class="sxs-lookup"><span data-stu-id="a5fda-140">Source File</span></span>|  
    |<span data-ttu-id="a5fda-141">Вторая метка</span><span class="sxs-lookup"><span data-stu-id="a5fda-141">Second label</span></span>|`Text`|<span data-ttu-id="a5fda-142">Сравнение строк</span><span class="sxs-lookup"><span data-stu-id="a5fda-142">Compare String</span></span>|  
    |<span data-ttu-id="a5fda-143">Третья метка</span><span class="sxs-lookup"><span data-stu-id="a5fda-143">Third label</span></span>|`Text`|<span data-ttu-id="a5fda-144">Совпадающие слова</span><span class="sxs-lookup"><span data-stu-id="a5fda-144">Matching Words</span></span>|  
    |<span data-ttu-id="a5fda-145">Четвертая метка</span><span class="sxs-lookup"><span data-stu-id="a5fda-145">Fourth label</span></span>|`Text`|<span data-ttu-id="a5fda-146">Число строк</span><span class="sxs-lookup"><span data-stu-id="a5fda-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="a5fda-147">Создание компонента BackgroundWorker и подписка на его события</span><span class="sxs-lookup"><span data-stu-id="a5fda-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="a5fda-148">Добавьте в форму компонент <xref:System.ComponentModel.BackgroundWorker> из раздела **Компоненты** в **панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="a5fda-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="a5fda-149">Он будет отображаться в области компонентов формы.</span><span class="sxs-lookup"><span data-stu-id="a5fda-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="a5fda-150">Задайте для объекта backgroundWorker1 следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="a5fda-150">Set the following properties for the backgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="a5fda-151">Свойство</span><span class="sxs-lookup"><span data-stu-id="a5fda-151">Property</span></span>|<span data-ttu-id="a5fda-152">Параметр</span><span class="sxs-lookup"><span data-stu-id="a5fda-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="a5fda-153">Да</span><span class="sxs-lookup"><span data-stu-id="a5fda-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="a5fda-154">Да</span><span class="sxs-lookup"><span data-stu-id="a5fda-154">True</span></span>|  
  
3.  <span data-ttu-id="a5fda-155">Подпишитесь на события объекта backgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="a5fda-155">Subscribe to the events of the backgroundWorker1 object.</span></span> <span data-ttu-id="a5fda-156">В верхней части окна **Свойства** нажмите на значок **События**.</span><span class="sxs-lookup"><span data-stu-id="a5fda-156">At the top of the **Properties** window, click the **Events** icon.</span></span> <span data-ttu-id="a5fda-157">Дважды щелкните событие `RunWorkerCompleted`, чтобы создать метод обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="a5fda-157">Double-click the `RunWorkerCompleted` event to create an event handler method.</span></span> <span data-ttu-id="a5fda-158">Сделайте то же самое для событий `ProgressChanged` и `DoWork`.</span><span class="sxs-lookup"><span data-stu-id="a5fda-158">Do the same for the `ProgressChanged` and `DoWork` events.</span></span>  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="a5fda-159">Определение метода, который будет выполняться в отдельном потоке</span><span class="sxs-lookup"><span data-stu-id="a5fda-159">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="a5fda-160">В меню **Проект** меню выберите пункт **Добавить класс**, чтобы добавить класс в проект.</span><span class="sxs-lookup"><span data-stu-id="a5fda-160">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="a5fda-161">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="a5fda-161">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="a5fda-162">Выберите **Класс** в окне "Шаблоны" и введите `Words.cs` в поле имени.</span><span class="sxs-lookup"><span data-stu-id="a5fda-162">Select **Class** from the templates window and enter `Words.cs` in the name field.</span></span>  
  
3.  <span data-ttu-id="a5fda-163">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a5fda-163">Click **Add**.</span></span> <span data-ttu-id="a5fda-164">Отобразится класс `Words`.</span><span class="sxs-lookup"><span data-stu-id="a5fda-164">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="a5fda-165">Добавьте следующий код в класс `Words` :</span><span class="sxs-lookup"><span data-stu-id="a5fda-165">Add the following code to the `Words` class:</span></span>  
  
    ```csharp  
    public class Words  
    {  
        // Object to store the current state, for passing to the caller.  
        public class CurrentState  
        {  
            public int LinesCounted;  
            public int WordsMatched;  
        }  
  
        public string SourceFile;  
        public string CompareString;  
        private int WordCount;  
        private int LinesCounted;  
  
        public void CountWords(  
            System.ComponentModel.BackgroundWorker worker,  
            System.ComponentModel.DoWorkEventArgs e)  
        {  
            // Initialize the variables.  
            CurrentState state = new CurrentState();  
            string line = "";  
            int elapsedTime = 20;  
            DateTime lastReportDateTime = DateTime.Now;  
  
            if (CompareString == null ||  
                CompareString == System.String.Empty)  
            {  
                throw new Exception("CompareString not specified.");  
            }  
  
            // Open a new stream.  
            using (System.IO.StreamReader myStream = new System.IO.StreamReader(SourceFile))  
            {  
                // Process lines while there are lines remaining in the file.  
                while (!myStream.EndOfStream)  
                {  
                    if (worker.CancellationPending)  
                    {  
                        e.Cancel = true;  
                        break;  
                    }  
                    else  
                    {  
                        line = myStream.ReadLine();  
                        WordCount += CountInString(line, CompareString);  
                        LinesCounted += 1;  
  
                        // Raise an event so the form can monitor progress.  
                        int compare = DateTime.Compare(  
                            DateTime.Now, lastReportDateTime.AddMilliseconds(elapsedTime));  
                        if (compare > 0)  
                        {  
                            state.LinesCounted = LinesCounted;  
                            state.WordsMatched = WordCount;  
                            worker.ReportProgress(0, state);  
                            lastReportDateTime = DateTime.Now;  
                        }  
                    }  
                    // Uncomment for testing.  
                    //System.Threading.Thread.Sleep(5);  
                }  
  
                // Report the final count values.  
                state.LinesCounted = LinesCounted;  
                state.WordsMatched = WordCount;  
                worker.ReportProgress(0, state);  
            }  
        }  
  
        private int CountInString(  
            string SourceString,  
            string CompareString)  
        {  
            // This function counts the number of times  
            // a word is found in a line.  
            if (SourceString == null)  
            {  
                return 0;  
            }  
  
            string EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString);  
  
            System.Text.RegularExpressions.Regex regex;  
            regex = new System.Text.RegularExpressions.Regex(   
                // To count all occurrences of the string, even within words, remove  
                // both instances of @"\b" from the following line.  
                @"\b" + EscapedCompareString + @"\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase);  
  
            System.Text.RegularExpressions.MatchCollection matches;  
            matches = regex.Matches(SourceString);  
            return matches.Count;  
        }  
  
    }  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="a5fda-166">Обработка событий из потока</span><span class="sxs-lookup"><span data-stu-id="a5fda-166">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="a5fda-167">Добавьте в основную форму следующие обработчики событий:</span><span class="sxs-lookup"><span data-stu-id="a5fda-167">Add the following event handlers to your main form:</span></span>  
  
    ```csharp  
    private void backgroundWorker1_RunWorkerCompleted(object sender, RunWorkerCompletedEventArgs e)  
    {  
    // This event handler is called when the background thread finishes.  
    // This method runs on the main thread.  
    if (e.Error != null)  
        MessageBox.Show("Error: " + e.Error.Message);  
    else if (e.Cancelled)  
        MessageBox.Show("Word counting canceled.");  
    else  
        MessageBox.Show("Finished counting words.");  
    }  
  
    private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)  
    {  
        // This method runs on the main thread.  
        Words.CurrentState state =  
            (Words.CurrentState)e.UserState;  
        this.LinesCounted.Text = state.LinesCounted.ToString();  
        this.WordsCounted.Text = state.WordsMatched.ToString();  
    }  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="a5fda-168">Запуск и вызов нового потока, выполняющего метод WordCount</span><span class="sxs-lookup"><span data-stu-id="a5fda-168">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="a5fda-169">Добавьте в программу следующие процедуры:</span><span class="sxs-lookup"><span data-stu-id="a5fda-169">Add the following procedures to your program:</span></span>  
  
    ```csharp  
    private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)  
    {  
        // This event handler is where the actual work is done.  
        // This method runs on the background thread.  
  
        // Get the BackgroundWorker object that raised this event.  
        System.ComponentModel.BackgroundWorker worker;  
        worker = (System.ComponentModel.BackgroundWorker)sender;  
  
        // Get the Words object and call the main method.  
        Words WC = (Words)e.Argument;  
        WC.CountWords(worker, e);  
    }  
  
    private void StartThread()  
    {  
        // This method runs on the main thread.  
        this.WordsCounted.Text = "0";  
  
        // Initialize the object that the background worker calls.  
        Words WC = new Words();  
        WC.CompareString = this.CompareString.Text;  
        WC.SourceFile = this.SourceFile.Text;  
  
        // Start the asynchronous operation.  
        backgroundWorker1.RunWorkerAsync(WC);  
    }  
    ```  
  
2.  <span data-ttu-id="a5fda-170">Вызовите метод `StartThread` из кнопки `Start` в вашей форме:</span><span class="sxs-lookup"><span data-stu-id="a5fda-170">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="a5fda-171">Реализация кнопки "Отмена", останавливающей поток</span><span class="sxs-lookup"><span data-stu-id="a5fda-171">To implement a Cancel button that stops the thread</span></span>  
  
    -   <span data-ttu-id="a5fda-172">Вызовите процедуру `StopThread` из обработчика событий `Click` для кнопки `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="a5fda-172">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
        ```  
  
## <a name="testing"></a><span data-ttu-id="a5fda-173">Тестирование</span><span class="sxs-lookup"><span data-stu-id="a5fda-173">Testing</span></span>  
 <span data-ttu-id="a5fda-174">Теперь вы можете протестировать приложение и убедиться в том, что оно работает правильно.</span><span class="sxs-lookup"><span data-stu-id="a5fda-174">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="a5fda-175">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="a5fda-175">To test the application</span></span>  
  
1.  <span data-ttu-id="a5fda-176">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="a5fda-176">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="a5fda-177">В открывшейся форме введите путь к файлу, который нужно протестировать, в поле `sourceFile`.</span><span class="sxs-lookup"><span data-stu-id="a5fda-177">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="a5fda-178">Например, если тестовый файл называется Test.txt, введите C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="a5fda-178">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="a5fda-179">Во втором текстовом поле введите слово или фразу для поиска приложения в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="a5fda-179">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="a5fda-180">Нажмите кнопку `Start`.</span><span class="sxs-lookup"><span data-stu-id="a5fda-180">Click the `Start` button.</span></span> <span data-ttu-id="a5fda-181">Значение на кнопке `LinesCounted` начнет увеличиваться незамедлительно.</span><span class="sxs-lookup"><span data-stu-id="a5fda-181">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="a5fda-182">По завершении в приложении отобразится сообщение "Подсчет завершен".</span><span class="sxs-lookup"><span data-stu-id="a5fda-182">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="a5fda-183">Тестирование кнопки "Отмена"</span><span class="sxs-lookup"><span data-stu-id="a5fda-183">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="a5fda-184">Нажмите клавишу F5 для запуска приложения, а затем введите имя файла и слово для поиска, как описано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="a5fda-184">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="a5fda-185">Убедитесь, что выбранный файл достаточно большой для того, чтобы процедуру можно было отменить до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="a5fda-185">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="a5fda-186">Нажмите кнопку `Start`, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="a5fda-186">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="a5fda-187">Нажмите кнопку `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="a5fda-187">Click the `Cancel` button.</span></span> <span data-ttu-id="a5fda-188">Приложение должно незамедлительно прекратить подсчет.</span><span class="sxs-lookup"><span data-stu-id="a5fda-188">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a5fda-189">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a5fda-189">Next Steps</span></span>  
 <span data-ttu-id="a5fda-190">Это приложение включает обработку некоторых основных ошибок.</span><span class="sxs-lookup"><span data-stu-id="a5fda-190">This application contains some basic error handling.</span></span> <span data-ttu-id="a5fda-191">Оно выявляет пустые строки поиска.</span><span class="sxs-lookup"><span data-stu-id="a5fda-191">It detects blank search strings.</span></span> <span data-ttu-id="a5fda-192">Программу можно сделать более надежной за счет обработки других ошибок, например, превышения максимального числа слов или строк, которые могут быть подсчитаны.</span><span class="sxs-lookup"><span data-stu-id="a5fda-192">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5fda-193">См. также</span><span class="sxs-lookup"><span data-stu-id="a5fda-193">See Also</span></span>  
 <span data-ttu-id="a5fda-194">[Работа с потоками (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="a5fda-194">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) </span></span>  
 [<span data-ttu-id="a5fda-195">Практическое руководство. Подписка и отмена подписки на события</span><span class="sxs-lookup"><span data-stu-id="a5fda-195">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
