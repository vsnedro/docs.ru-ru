---
title: Классы и объекты. Вводное руководство по C#.
description: Создайте свою первую программу на C# и ознакомьтесь с основными понятиями объектно-ориентированного программирования
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 5edb2d7b11caace2d794b7958dfeb75ef502ee2b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396866"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="c9518-103">Сведения об использовании классов и объектов в объектно-ориентированном программировании</span><span class="sxs-lookup"><span data-stu-id="c9518-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="c9518-104">Для работы с этим руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="c9518-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="c9518-105">В руководстве .NET по созданию программы [Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="c9518-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="c9518-106">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в статье, посвященной [средствам разработки для .NET](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c9518-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="c9518-107">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="c9518-107">Create your application</span></span>

<span data-ttu-id="c9518-108">С помощью окна терминала создайте каталог с именем *classes*.</span><span class="sxs-lookup"><span data-stu-id="c9518-108">Using a terminal window, create a directory named *classes*.</span></span> <span data-ttu-id="c9518-109">В этом каталоге вы создадите приложение.</span><span class="sxs-lookup"><span data-stu-id="c9518-109">You'll build your application there.</span></span> <span data-ttu-id="c9518-110">Откройте этот каталог и введите в окне консоли `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="c9518-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="c9518-111">При помощи этой команды создается приложение.</span><span class="sxs-lookup"><span data-stu-id="c9518-111">This command creates your application.</span></span> <span data-ttu-id="c9518-112">Откройте файл *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="c9518-112">Open *Program.cs*.</span></span> <span data-ttu-id="c9518-113">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="c9518-113">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="c9518-114">При работе с этим руководством вы создадите новые типы, представляющие банковский счет.</span><span class="sxs-lookup"><span data-stu-id="c9518-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="c9518-115">Обычно разработчики определяют каждый класс в отдельном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="c9518-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="c9518-116">Благодаря этому программой легче управлять, когда ее размер увеличивается.</span><span class="sxs-lookup"><span data-stu-id="c9518-116">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="c9518-117">Создайте новый файл с именем *BankAccount.cs* в каталоге *classes*.</span><span class="sxs-lookup"><span data-stu-id="c9518-117">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span>

<span data-ttu-id="c9518-118">Этот файл будет содержать определение ***банковского счета***.</span><span class="sxs-lookup"><span data-stu-id="c9518-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="c9518-119">Средства объектно-ориентированного программирования обеспечивают упорядочение кода. При этом создаются типы в виде ***классов***.</span><span class="sxs-lookup"><span data-stu-id="c9518-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="c9518-120">Классы содержат код, который представляет отдельную сущность.</span><span class="sxs-lookup"><span data-stu-id="c9518-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="c9518-121">Класс `BankAccount` представляет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="c9518-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="c9518-122">Этот код реализует определенные операции с помощью методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="c9518-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="c9518-123">Созданный в этом кратком руководстве банковский счет поддерживает следующий алгоритм работы:</span><span class="sxs-lookup"><span data-stu-id="c9518-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="c9518-124">Представляет собой число из 10 цифр, которое однозначно определяет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="c9518-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="c9518-125">Содержит строку, в которой хранятся имена владельцев.</span><span class="sxs-lookup"><span data-stu-id="c9518-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="c9518-126">Позволяет получить данные сальдо.</span><span class="sxs-lookup"><span data-stu-id="c9518-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="c9518-127">Принимает депозиты.</span><span class="sxs-lookup"><span data-stu-id="c9518-127">It accepts deposits.</span></span>
1. <span data-ttu-id="c9518-128">Принимает списания.</span><span class="sxs-lookup"><span data-stu-id="c9518-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="c9518-129">Начальное сальдо должно было положительным.</span><span class="sxs-lookup"><span data-stu-id="c9518-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="c9518-130">После списания не должно оставаться отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="c9518-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="c9518-131">Определение типа банковского счета</span><span class="sxs-lookup"><span data-stu-id="c9518-131">Define the bank account type</span></span>

<span data-ttu-id="c9518-132">Сначала можно создать основы класса, который определяет такой режим работы.</span><span class="sxs-lookup"><span data-stu-id="c9518-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="c9518-133">Создайте новый файл с помощью команды **File:New**.</span><span class="sxs-lookup"><span data-stu-id="c9518-133">Create a new file using the **File:New** command.</span></span> <span data-ttu-id="c9518-134">Присвойте ему имя *BankAccount.cs*.</span><span class="sxs-lookup"><span data-stu-id="c9518-134">Name it *BankAccount.cs*.</span></span> <span data-ttu-id="c9518-135">Добавьте в файл *BankAccount.cs* следующий код:</span><span class="sxs-lookup"><span data-stu-id="c9518-135">Add the following code to your *BankAccount.cs* file:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="c9518-136">Прежде чем продолжить, рассмотрим созданный код.</span><span class="sxs-lookup"><span data-stu-id="c9518-136">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="c9518-137">Объявление `namespace` предоставляет способ логического упорядочения кода.</span><span class="sxs-lookup"><span data-stu-id="c9518-137">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="c9518-138">Это относительно небольшое руководство, поэтому весь код размещается в одном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="c9518-138">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span>

<span data-ttu-id="c9518-139">`public class BankAccount` определяет класс или тип, который вы создаете.</span><span class="sxs-lookup"><span data-stu-id="c9518-139">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="c9518-140">Весь код в скобках `{` и `}`, который следует за объявлением класса, определяет состояние и поведение класса.</span><span class="sxs-lookup"><span data-stu-id="c9518-140">Everything inside the `{` and `}` that follows the class declaration defines the state and behavior of the class.</span></span> <span data-ttu-id="c9518-141">Есть пять ***элементов*** класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="c9518-141">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="c9518-142">Первые три элемента представляют собой ***свойства***.</span><span class="sxs-lookup"><span data-stu-id="c9518-142">The first three are ***properties***.</span></span> <span data-ttu-id="c9518-143">Свойства являются элементами данных и могут содержать код для запуска проверки или других правил.</span><span class="sxs-lookup"><span data-stu-id="c9518-143">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="c9518-144">Последние два элемента являются ***методами***.</span><span class="sxs-lookup"><span data-stu-id="c9518-144">The last two are ***methods***.</span></span> <span data-ttu-id="c9518-145">Методы представляют собой блоки кода, которые выполняют только одну функцию.</span><span class="sxs-lookup"><span data-stu-id="c9518-145">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="c9518-146">Имя каждого элемента должно содержать достаточно информации, чтобы разработчик мог понять, какие функции выполняет класс.</span><span class="sxs-lookup"><span data-stu-id="c9518-146">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="c9518-147">Открытие нового счета</span><span class="sxs-lookup"><span data-stu-id="c9518-147">Open a new account</span></span>

<span data-ttu-id="c9518-148">Сначала нужно открыть банковский счет.</span><span class="sxs-lookup"><span data-stu-id="c9518-148">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="c9518-149">Когда клиент открывает счет, он должен указать начальное сальдо и сведения о владельцах этого счета.</span><span class="sxs-lookup"><span data-stu-id="c9518-149">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span>

<span data-ttu-id="c9518-150">Создайте новый объект типа `BankAccount`, чтобы определить ***конструктор***, который назначает эти значения.</span><span class="sxs-lookup"><span data-stu-id="c9518-150">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="c9518-151">***Конструктор*** — это элемент, имя которого совпадает с классом.</span><span class="sxs-lookup"><span data-stu-id="c9518-151">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="c9518-152">Он используется для инициализации объектов этого типа класса.</span><span class="sxs-lookup"><span data-stu-id="c9518-152">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="c9518-153">Добавьте указанный ниже конструктор в тип `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="c9518-153">Add the following constructor to the `BankAccount` type.</span></span> <span data-ttu-id="c9518-154">Добавьте следующий код непосредственно перед объявлением `MakeDeposit`:</span><span class="sxs-lookup"><span data-stu-id="c9518-154">Place the following code above the declaration of `MakeDeposit`:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="c9518-155">Конструкторы вызываются при создании объекта с помощью [`new`](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c9518-155">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="c9518-156">Замените строку `Console.WriteLine("Hello World!");` в файле *Program.cs* следующим кодом (замените `<name>` своим именем):</span><span class="sxs-lookup"><span data-stu-id="c9518-156">Replace the line `Console.WriteLine("Hello World!");` in *Program.cs* with the following code (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="c9518-157">Давайте выполним то, что уже создано.</span><span class="sxs-lookup"><span data-stu-id="c9518-157">Let's run what you've built so far.</span></span> <span data-ttu-id="c9518-158">Если вы работаете в Visual Studio, выберите **Запуск без отладки** из меню **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c9518-158">If you're using Visual Studio, Select **Start without debugging** from the **Run** menu.</span></span> <span data-ttu-id="c9518-159">Если вы используете командную строку, введите `dotnet run` в том каталоге, где создали проект.</span><span class="sxs-lookup"><span data-stu-id="c9518-159">If you're using a command line, type `dotnet run` in the directory where you've created your project.</span></span>

<span data-ttu-id="c9518-160">Вы заметили, что номер счета не указан?</span><span class="sxs-lookup"><span data-stu-id="c9518-160">Did you notice that the account number is blank?</span></span> <span data-ttu-id="c9518-161">Нужно решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="c9518-161">It's time to fix that.</span></span> <span data-ttu-id="c9518-162">Номер счета следует назначить при создании объекта.</span><span class="sxs-lookup"><span data-stu-id="c9518-162">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="c9518-163">Но создавать этот номер не входит в обязанности вызывающего.</span><span class="sxs-lookup"><span data-stu-id="c9518-163">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="c9518-164">Код класса `BankAccount` должен иметь информацию о том, как присвоить номера новым счетам.</span><span class="sxs-lookup"><span data-stu-id="c9518-164">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="c9518-165">Проще всего начать с 10-значного числа.</span><span class="sxs-lookup"><span data-stu-id="c9518-165">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="c9518-166">Увеличивайте его при создании каждого нового счета.</span><span class="sxs-lookup"><span data-stu-id="c9518-166">Increment it when each new account is created.</span></span> <span data-ttu-id="c9518-167">Затем при создании объекта сохраните номер текущего счета.</span><span class="sxs-lookup"><span data-stu-id="c9518-167">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="c9518-168">Добавьте в класс `BankAccount` объявление члена.</span><span class="sxs-lookup"><span data-stu-id="c9518-168">Add a member declaration to the `BankAccount` class.</span></span> <span data-ttu-id="c9518-169">Поместите следующую строку кода после открывающей скобки `{` в начале класса `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="c9518-169">Place the following line of code after the opening brace `{` at the beginning of the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="c9518-170">Это элемент данных.</span><span class="sxs-lookup"><span data-stu-id="c9518-170">This is a data member.</span></span> <span data-ttu-id="c9518-171">Он имеет свойство `private`, то есть к нему может получить доступ только код внутри класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="c9518-171">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="c9518-172">Таким образом общедоступные обязательства (например, получение номера счета) отделяются от закрытой реализации (способ создания номеров счетов).</span><span class="sxs-lookup"><span data-stu-id="c9518-172">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated).</span></span> <span data-ttu-id="c9518-173">Также он является `static`, то есть совместно используется всеми объектами `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="c9518-173">It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="c9518-174">Значение нестатической переменной является уникальным для каждого экземпляра объекта `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="c9518-174">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="c9518-175">Добавьте две приведенные ниже строки в конструктор, чтобы назначить номер счета.</span><span class="sxs-lookup"><span data-stu-id="c9518-175">Add the following two lines to the constructor to assign the account number.</span></span> <span data-ttu-id="c9518-176">Они должны располагаться за строкой с текстом `this.Balance = initialBalance`.</span><span class="sxs-lookup"><span data-stu-id="c9518-176">Place them after the line that says `this.Balance = initialBalance`:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="c9518-177">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="c9518-177">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="c9518-178">Создание депозитов и списаний</span><span class="sxs-lookup"><span data-stu-id="c9518-178">Create deposits and withdrawals</span></span>

<span data-ttu-id="c9518-179">Для надлежащей работы ваш класс банковского счета должен принимать депозиты и списания.</span><span class="sxs-lookup"><span data-stu-id="c9518-179">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="c9518-180">Чтобы реализовать депозиты и списания, создадим журнал для каждой транзакции на счете.</span><span class="sxs-lookup"><span data-stu-id="c9518-180">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="c9518-181">Этот подход предпочтительнее, чем простое обновление сальдо после каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="c9518-181">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="c9518-182">Журнал можно использовать для аудита всех транзакций и управления ежедневным сальдо.</span><span class="sxs-lookup"><span data-stu-id="c9518-182">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="c9518-183">При необходимости можно вычислять сальдо с помощью журнала всех транзакций. Тогда при следующем вычислении все исправленные ошибки в одной транзакции будут правильно учтены в сальдо.</span><span class="sxs-lookup"><span data-stu-id="c9518-183">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="c9518-184">Начнем с создания нового типа, который представляет транзакцию.</span><span class="sxs-lookup"><span data-stu-id="c9518-184">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="c9518-185">Это простой тип без обязательств.</span><span class="sxs-lookup"><span data-stu-id="c9518-185">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="c9518-186">Ему нужно назначить несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="c9518-186">It needs a few properties.</span></span> <span data-ttu-id="c9518-187">Создайте новый файл с именем *Transaction.cs*.</span><span class="sxs-lookup"><span data-stu-id="c9518-187">Create a new file named *Transaction.cs*.</span></span> <span data-ttu-id="c9518-188">Добавьте в этот файл следующий код:</span><span class="sxs-lookup"><span data-stu-id="c9518-188">Add the following code to it:</span></span>

[!code-csharp[Transaction](~/samples/snippets/csharp/classes-quickstart/Transaction.cs)]

<span data-ttu-id="c9518-189">Теперь добавим <xref:System.Collections.Generic.List%601> объектов `Transaction` в класс `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="c9518-189">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="c9518-190">Добавьте следующее объявление после конструктора в файл *BankAccount.cs*:</span><span class="sxs-lookup"><span data-stu-id="c9518-190">Add the following declaration after the constructor in your *BankAccount.cs* file:</span></span>

[!code-csharp[TransactionDecl](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration)]

<span data-ttu-id="c9518-191">Класс <xref:System.Collections.Generic.List%601> требует импортировать другое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="c9518-191">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="c9518-192">Добавьте следующий код в начало файла *BankAccount.cs*:</span><span class="sxs-lookup"><span data-stu-id="c9518-192">Add the following at the beginning of *BankAccount.cs*:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="c9518-193">Теперь изменим способ отчета `Balance`.</span><span class="sxs-lookup"><span data-stu-id="c9518-193">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="c9518-194">Чтобы вычислить его, нужно суммировать значения всех транзакций.</span><span class="sxs-lookup"><span data-stu-id="c9518-194">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="c9518-195">Измените объявление `Balance` в классе `BankAccount` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c9518-195">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#BalanceComputation)]

<span data-ttu-id="c9518-196">В этом примере показан важный аспект ***свойств***.</span><span class="sxs-lookup"><span data-stu-id="c9518-196">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="c9518-197">Вы вычисляете сальдо, когда другой программист запрашивает значение.</span><span class="sxs-lookup"><span data-stu-id="c9518-197">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="c9518-198">В результате вашего вычисления выводится список всех транзакций и сумма в виде текущего сальдо.</span><span class="sxs-lookup"><span data-stu-id="c9518-198">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="c9518-199">Теперь реализуйте методы `MakeDeposit` и `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="c9518-199">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="c9518-200">Эти методы будут выполнять два последних правила: начальное сальдо должно быть положительным, списание не должно создавать отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="c9518-200">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span>

<span data-ttu-id="c9518-201">Это действие вводит понятие ***исключений***.</span><span class="sxs-lookup"><span data-stu-id="c9518-201">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="c9518-202">Чтобы определить, что метод не может выполнить свою функцию, обычно вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="c9518-202">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="c9518-203">В типе исключения и связанном с ним сообщении описывается ошибка.</span><span class="sxs-lookup"><span data-stu-id="c9518-203">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="c9518-204">В этом примере метод `MakeDeposit` вызывает исключение, если сумма депозита является отрицательной.</span><span class="sxs-lookup"><span data-stu-id="c9518-204">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="c9518-205">Метод `MakeWithdrawal` вызывает исключение, если сумма списания является отрицательной или если при списании создается отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="c9518-205">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance.</span></span> <span data-ttu-id="c9518-206">Добавьте следующий код после объявления списка `allTransactions`:</span><span class="sxs-lookup"><span data-stu-id="c9518-206">Add the following code after the declaration of the `allTransactions` list:</span></span>

[!code-csharp[DepositAndWithdrawal](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal)]

<span data-ttu-id="c9518-207">Инструкция [`throw`](../../language-reference/keywords/throw.md)**вызывает** исключение.</span><span class="sxs-lookup"><span data-stu-id="c9518-207">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="c9518-208">Выполнение текущего блока завершается и управление передается в первый подходящий блок `catch` из стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="c9518-208">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="c9518-209">Вы добавите блок `catch` для тестирования этого кода немного позже.</span><span class="sxs-lookup"><span data-stu-id="c9518-209">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="c9518-210">Чтобы вместо непосредственного обновления сальдо добавлялась начальная транзакция, конструктор должен получить одно изменение.</span><span class="sxs-lookup"><span data-stu-id="c9518-210">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="c9518-211">Так как вы уже написали метод `MakeDeposit`, вызовите его из конструктора.</span><span class="sxs-lookup"><span data-stu-id="c9518-211">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="c9518-212">Готовый конструктор должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="c9518-212">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#Constructor)]

<span data-ttu-id="c9518-213"><xref:System.DateTime.Now?displayProperty=nameWithType> — это свойство, которое возвращает текущие дату и время.</span><span class="sxs-lookup"><span data-stu-id="c9518-213"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="c9518-214">Проверьте его. Для этого добавьте несколько депозитов и списаний в метод `Main` после кода, с помощью которого создается `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="c9518-214">Test this by adding a few deposits and withdrawals in your `Main` method, following the code that creates a new `BankAccount`:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="c9518-215">Теперь убедитесь, что условия возникновения ошибки срабатывают правильно, создав счет с отрицательным сальдо.</span><span class="sxs-lookup"><span data-stu-id="c9518-215">Next, test that you are catching error conditions by trying to create an account with a negative balance.</span></span> <span data-ttu-id="c9518-216">Добавьте следующий код после только что добавленного блока кода:</span><span class="sxs-lookup"><span data-stu-id="c9518-216">Add the following code after the preceding code you just added:</span></span>

```csharp
// Test that the initial balances must be positive.
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="c9518-217">С помощью [инструкций `try` и `catch`](../../language-reference/keywords/try-catch.md) пометьте блок кода, который может вызывать исключения, и перехватывайте ожидаемые сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c9518-217">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="c9518-218">Так же можно проверять код, который вызывает исключение при получении отрицательного баланса.</span><span class="sxs-lookup"><span data-stu-id="c9518-218">You can use the same technique to test the code that throws an exception for a negative balance.</span></span> <span data-ttu-id="c9518-219">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="c9518-219">Add the following code at the end of your `Main` method:</span></span>

```csharp
// Test for a negative balance.
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="c9518-220">Сохраните файл и введите `dotnet run` для проверки.</span><span class="sxs-lookup"><span data-stu-id="c9518-220">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="c9518-221">Задача — регистрация всех транзакций</span><span class="sxs-lookup"><span data-stu-id="c9518-221">Challenge - log all transactions</span></span>

<span data-ttu-id="c9518-222">В завершение вы создадите метод `GetAccountHistory`, который создает `string` для журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="c9518-222">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="c9518-223">Добавьте этот метод в тип `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="c9518-223">Add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#History)]

<span data-ttu-id="c9518-224">В этом примере используется класс <xref:System.Text.StringBuilder>, чтобы отформатировать строку, которая содержит одну строку для каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="c9518-224">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="c9518-225">Код форматирования строки вы уже видели в этой серии руководств.</span><span class="sxs-lookup"><span data-stu-id="c9518-225">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="c9518-226">В этом коде есть новый символ `\t`.</span><span class="sxs-lookup"><span data-stu-id="c9518-226">One new character is `\t`.</span></span> <span data-ttu-id="c9518-227">Он позволяет вставить вкладку для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c9518-227">That inserts a tab to format the output.</span></span>

<span data-ttu-id="c9518-228">Добавьте следующую строку, чтобы проверить его в файле *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="c9518-228">Add this line to test it in *Program.cs*:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="c9518-229">Снова выполните программу, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="c9518-229">Run your program to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9518-230">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c9518-230">Next steps</span></span>

<span data-ttu-id="c9518-231">Если у вас возникли проблемы, изучите исходный код для этого руководства, размещенный [в репозитории GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/classes-quickstart/).</span><span class="sxs-lookup"><span data-stu-id="c9518-231">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/classes-quickstart/).</span></span>

<span data-ttu-id="c9518-232">Поздравляем, вы завершили работу с циклом вводных руководств по C#.</span><span class="sxs-lookup"><span data-stu-id="c9518-232">Congratulations, you've finished all our introduction to C# tutorials.</span></span> <span data-ttu-id="c9518-233">Если вы хотите узнать больше, обратитесь к другим [руководствам](../index.md).</span><span class="sxs-lookup"><span data-stu-id="c9518-233">If you're eager to learn more, try more of our [tutorials](../index.md).</span></span>
