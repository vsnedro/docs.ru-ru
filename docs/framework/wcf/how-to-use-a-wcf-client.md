---
title: Учебник. Использование клиента Windows Communication Foundation
description: Узнайте, как создать экземпляр клиента, скомпилировать приложение и взаимодействовать со службой в рамках серии статей, посвященных созданию приложения WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 5c94d5f8af679580c4194aaaadeda759098953d2
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244339"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="ff23e-103">Учебник. Использование клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ff23e-103">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="ff23e-104">В этом руководстве описываются пять задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ff23e-104">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="ff23e-105">Общие сведения о учебниках см. в разделе [учебник. Начало работы с Windows Communication Foundation приложениями](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ff23e-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="ff23e-106">После создания и настройки прокси-сервера Windows Communication Foundation (WCF) необходимо создать экземпляр клиента и скомпилировать клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="ff23e-106">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="ff23e-107">Затем его можно использовать для взаимодействия со службой WCF.</span><span class="sxs-lookup"><span data-stu-id="ff23e-107">You then use it to communicate with the WCF service.</span></span>

<span data-ttu-id="ff23e-108">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="ff23e-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ff23e-109">Добавьте код для использования клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="ff23e-109">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="ff23e-110">Протестируйте клиент WCF.</span><span class="sxs-lookup"><span data-stu-id="ff23e-110">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="ff23e-111">Добавление кода для использования клиента WCF</span><span class="sxs-lookup"><span data-stu-id="ff23e-111">Add code to use the WCF client</span></span>

<span data-ttu-id="ff23e-112">Клиентский код выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ff23e-112">The client code does the following steps:</span></span>

- <span data-ttu-id="ff23e-113">Создает экземпляр клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="ff23e-113">Instantiates the WCF client.</span></span>
- <span data-ttu-id="ff23e-114">Вызывает операции службы из созданной учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="ff23e-114">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="ff23e-115">Закрывает клиент после завершения вызова операции.</span><span class="sxs-lookup"><span data-stu-id="ff23e-115">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="ff23e-116">Откройте файл **Program.CS** или **Module1. vb** из проекта **GettingStartedClient** и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="ff23e-116">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

<span data-ttu-id="ff23e-117">Обратите внимание на `using` инструкцию (для Visual C#) или `Imports` (for Visual Basic), которая импортирует `GettingStartedClient.ServiceReference1` .</span><span class="sxs-lookup"><span data-stu-id="ff23e-117">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="ff23e-118">Эта инструкция импортирует код, созданный Visual Studio с помощью функции **Добавление ссылки на службу** .</span><span class="sxs-lookup"><span data-stu-id="ff23e-118">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="ff23e-119">Код создает прокси-сервер WCF и вызывает каждую из операций службы, предоставляемых службой калькулятора.</span><span class="sxs-lookup"><span data-stu-id="ff23e-119">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="ff23e-120">Затем он закрывает прокси-сервер и завершает программу.</span><span class="sxs-lookup"><span data-stu-id="ff23e-120">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="ff23e-121">Тестирование клиента WCF</span><span class="sxs-lookup"><span data-stu-id="ff23e-121">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="ff23e-122">Тестирование приложения из Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ff23e-122">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="ff23e-123">Сохраните решение и выполните его построение.</span><span class="sxs-lookup"><span data-stu-id="ff23e-123">Save and build the solution.</span></span>

2. <span data-ttu-id="ff23e-124">Выберите папку **жеттингстартедлиб** , а затем в контекстном меню выберите **Назначить запускаемым проектом** .</span><span class="sxs-lookup"><span data-stu-id="ff23e-124">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="ff23e-125">В **меню запускаемые проекты**выберите **жеттингстартедлиб** из раскрывающегося списка, а затем выберите **выполнить** или нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="ff23e-125">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="ff23e-126">Тестирование приложения из командной строки</span><span class="sxs-lookup"><span data-stu-id="ff23e-126">Test the application from a command prompt</span></span>

1. <span data-ttu-id="ff23e-127">Откройте командную строку от имени администратора и перейдите к каталогу решения Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ff23e-127">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span>

2. <span data-ttu-id="ff23e-128">Чтобы запустить службу, введите *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span><span class="sxs-lookup"><span data-stu-id="ff23e-128">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="ff23e-129">Чтобы запустить клиент: Откройте еще одну командную строку, перейдите в каталог решения Visual Studio и введите *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span><span class="sxs-lookup"><span data-stu-id="ff23e-129">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="ff23e-130">*GettingStartedHost.exe* выдает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="ff23e-130">*GettingStartedHost.exe* produces the following output:</span></span>

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   <span data-ttu-id="ff23e-131">*GettingStartedClient.exe* выдает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="ff23e-131">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="ff23e-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ff23e-132">Next steps</span></span>

<span data-ttu-id="ff23e-133">Теперь вы выполнили все задачи в руководстве по началу работы с WCF.</span><span class="sxs-lookup"><span data-stu-id="ff23e-133">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="ff23e-134">В этом руководстве вы узнали, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="ff23e-134">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="ff23e-135">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="ff23e-135">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ff23e-136">Добавьте код для использования клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="ff23e-136">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="ff23e-137">Протестируйте клиент WCF.</span><span class="sxs-lookup"><span data-stu-id="ff23e-137">Test the WCF client.</span></span>

<span data-ttu-id="ff23e-138">При возникновении проблем или ошибок во всех шагах выполните действия, описанные в статье Устранение неполадок, чтобы устранить их.</span><span class="sxs-lookup"><span data-stu-id="ff23e-138">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ff23e-139">Устранение неполадок в учебниках Приступая к работе с WCF</span><span class="sxs-lookup"><span data-stu-id="ff23e-139">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
