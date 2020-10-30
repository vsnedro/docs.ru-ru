---
title: Классы и объекты. Вводное руководство по C#.
description: Создайте свою первую программу на C# и ознакомьтесь с основными понятиями объектно-ориентированного программирования
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 0955b0ac33b346b9880c8af70bd73cb458120f35
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434893"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="25464-103">Сведения об использовании классов и объектов в объектно-ориентированном программировании</span><span class="sxs-lookup"><span data-stu-id="25464-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="25464-104">Для работы с этим руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="25464-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="25464-105">В руководстве .NET по созданию программы [Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="25464-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="25464-106">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в статье, посвященной [средствам разработки для .NET](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="25464-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="25464-107">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="25464-107">Create your application</span></span>

<span data-ttu-id="25464-108">С помощью окна терминала создайте каталог с именем *classes* .</span><span class="sxs-lookup"><span data-stu-id="25464-108">Using a terminal window, create a directory named *classes* .</span></span> <span data-ttu-id="25464-109">В этом каталоге вы создадите приложение.</span><span class="sxs-lookup"><span data-stu-id="25464-109">You'll build your application there.</span></span> <span data-ttu-id="25464-110">Откройте этот каталог и введите в окне консоли `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="25464-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="25464-111">При помощи этой команды создается приложение.</span><span class="sxs-lookup"><span data-stu-id="25464-111">This command creates your application.</span></span> <span data-ttu-id="25464-112">Откройте файл *Program.cs* .</span><span class="sxs-lookup"><span data-stu-id="25464-112">Open *Program.cs* .</span></span> <span data-ttu-id="25464-113">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="25464-113">It should look like this:</span></span>

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

<span data-ttu-id="25464-114">При работе с этим руководством вы создадите новые типы, представляющие банковский счет.</span><span class="sxs-lookup"><span data-stu-id="25464-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="25464-115">Обычно разработчики определяют каждый класс в отдельном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="25464-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="25464-116">Благодаря этому программой легче управлять, когда ее размер увеличивается.</span><span class="sxs-lookup"><span data-stu-id="25464-116">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="25464-117">Создайте новый файл с именем *BankAccount.cs* в каталоге *classes* .</span><span class="sxs-lookup"><span data-stu-id="25464-117">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span>

<span data-ttu-id="25464-118">Этот файл будет содержать определение \* **банковского счета** _.</span><span class="sxs-lookup"><span data-stu-id="25464-118">This file will contain the definition of a \* **bank account** _.</span></span> <span data-ttu-id="25464-119">Средства объектно-ориентированного программирования обеспечивают упорядочение кода. При этом создаются типы в виде _\*_классов_\*_ .</span><span class="sxs-lookup"><span data-stu-id="25464-119">Object Oriented programming organizes code by creating types in the form of _*_classes_*_ .</span></span> <span data-ttu-id="25464-120">Классы содержат код, который представляет отдельную сущность.</span><span class="sxs-lookup"><span data-stu-id="25464-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="25464-121">Класс `BankAccount` представляет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="25464-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="25464-122">Этот код реализует определенные операции с помощью методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="25464-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="25464-123">Созданный в этом кратком руководстве банковский счет поддерживает следующий алгоритм работы:</span><span class="sxs-lookup"><span data-stu-id="25464-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="25464-124">Представляет собой число из 10 цифр, которое однозначно определяет банковский счет.</span><span class="sxs-lookup"><span data-stu-id="25464-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="25464-125">Содержит строку, в которой хранятся имена владельцев.</span><span class="sxs-lookup"><span data-stu-id="25464-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="25464-126">Позволяет получить данные сальдо.</span><span class="sxs-lookup"><span data-stu-id="25464-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="25464-127">Принимает депозиты.</span><span class="sxs-lookup"><span data-stu-id="25464-127">It accepts deposits.</span></span>
1. <span data-ttu-id="25464-128">Принимает списания.</span><span class="sxs-lookup"><span data-stu-id="25464-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="25464-129">Начальное сальдо должно было положительным.</span><span class="sxs-lookup"><span data-stu-id="25464-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="25464-130">После списания не должно оставаться отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="25464-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="25464-131">Определение типа банковского счета</span><span class="sxs-lookup"><span data-stu-id="25464-131">Define the bank account type</span></span>

<span data-ttu-id="25464-132">Сначала можно создать основы класса, который определяет такой режим работы.</span><span class="sxs-lookup"><span data-stu-id="25464-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="25464-133">Создайте новый файл с помощью команды _ *File:New* \*.</span><span class="sxs-lookup"><span data-stu-id="25464-133">Create a new file using the _ *File:New* \* command.</span></span> <span data-ttu-id="25464-134">Присвойте ему имя *BankAccount.cs* .</span><span class="sxs-lookup"><span data-stu-id="25464-134">Name it *BankAccount.cs* .</span></span> <span data-ttu-id="25464-135">Добавьте в файл *BankAccount.cs* следующий код:</span><span class="sxs-lookup"><span data-stu-id="25464-135">Add the following code to your *BankAccount.cs* file:</span></span>

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

<span data-ttu-id="25464-136">Прежде чем продолжить, рассмотрим созданный код.</span><span class="sxs-lookup"><span data-stu-id="25464-136">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="25464-137">Объявление `namespace` предоставляет способ логического упорядочения кода.</span><span class="sxs-lookup"><span data-stu-id="25464-137">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="25464-138">Это относительно небольшое руководство, поэтому весь код размещается в одном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="25464-138">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span>

<span data-ttu-id="25464-139">`public class BankAccount` определяет класс или тип, который вы создаете.</span><span class="sxs-lookup"><span data-stu-id="25464-139">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="25464-140">Весь код в скобках `{` и `}`, который следует за объявлением класса, определяет состояние и поведение класса.</span><span class="sxs-lookup"><span data-stu-id="25464-140">Everything inside the `{` and `}` that follows the class declaration defines the state and behavior of the class.</span></span> <span data-ttu-id="25464-141">Есть пять \* **элементов** _ класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="25464-141">There are five \* **members** _ of the `BankAccount` class.</span></span> <span data-ttu-id="25464-142">Первые три элемента представляют собой _\*_свойства_\*_ .</span><span class="sxs-lookup"><span data-stu-id="25464-142">The first three are _*_properties_*_ .</span></span> <span data-ttu-id="25464-143">Свойства являются элементами данных и могут содержать код для запуска проверки или других правил.</span><span class="sxs-lookup"><span data-stu-id="25464-143">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="25464-144">Последние два элемента являются _\*_методами_\*_ .</span><span class="sxs-lookup"><span data-stu-id="25464-144">The last two are _*_methods_*_ .</span></span> <span data-ttu-id="25464-145">Методы представляют собой блоки кода, которые выполняют только одну функцию.</span><span class="sxs-lookup"><span data-stu-id="25464-145">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="25464-146">Имя каждого элемента должно содержать достаточно информации, чтобы разработчик мог понять, какие функции выполняет класс.</span><span class="sxs-lookup"><span data-stu-id="25464-146">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="25464-147">Открытие нового счета</span><span class="sxs-lookup"><span data-stu-id="25464-147">Open a new account</span></span>

<span data-ttu-id="25464-148">Сначала нужно открыть банковский счет.</span><span class="sxs-lookup"><span data-stu-id="25464-148">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="25464-149">Когда клиент открывает счет, он должен указать начальное сальдо и сведения о владельцах этого счета.</span><span class="sxs-lookup"><span data-stu-id="25464-149">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span>

<span data-ttu-id="25464-150">Создайте новый объект типа `BankAccount`, чтобы определить _\*_конструктор_\*_ , который назначает эти значения.</span><span class="sxs-lookup"><span data-stu-id="25464-150">Creating a new object of the `BankAccount` type means defining a _*_constructor_*_ that assigns those values.</span></span> <span data-ttu-id="25464-151">_\*_Конструктор_\*_  — это элемент, имя которого совпадает с классом.</span><span class="sxs-lookup"><span data-stu-id="25464-151">A _*_constructor_*_ is a member that has the same name as the class.</span></span> <span data-ttu-id="25464-152">Он используется для инициализации объектов этого типа класса.</span><span class="sxs-lookup"><span data-stu-id="25464-152">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="25464-153">Добавьте указанный ниже конструктор в тип `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="25464-153">Add the following constructor to the `BankAccount` type.</span></span> <span data-ttu-id="25464-154">Добавьте следующий код непосредственно перед объявлением `MakeDeposit`:</span><span class="sxs-lookup"><span data-stu-id="25464-154">Place the following code above the declaration of `MakeDeposit`:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="25464-155">Конструкторы вызываются при создании объекта с помощью [`new`](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="25464-155">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="25464-156">Замените строку `Console.WriteLine("Hello World!");` в файле _Program.cs\* следующим кодом (замените `<name>` своим именем):</span><span class="sxs-lookup"><span data-stu-id="25464-156">Replace the line `Console.WriteLine("Hello World!");` in _Program.cs\* with the following code (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="25464-157">Давайте выполним то, что уже создано.</span><span class="sxs-lookup"><span data-stu-id="25464-157">Let's run what you've built so far.</span></span> <span data-ttu-id="25464-158">Если вы работаете в Visual Studio, выберите **Запуск без отладки** из меню **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="25464-158">If you're using Visual Studio, Select **Start without debugging** from the **Run** menu.</span></span> <span data-ttu-id="25464-159">Если вы используете командную строку, введите `dotnet run` в том каталоге, где создали проект.</span><span class="sxs-lookup"><span data-stu-id="25464-159">If you're using a command line, type `dotnet run` in the directory where you've created your project.</span></span>

<span data-ttu-id="25464-160">Вы заметили, что номер счета не указан?</span><span class="sxs-lookup"><span data-stu-id="25464-160">Did you notice that the account number is blank?</span></span> <span data-ttu-id="25464-161">Нужно решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="25464-161">It's time to fix that.</span></span> <span data-ttu-id="25464-162">Номер счета следует назначить при создании объекта.</span><span class="sxs-lookup"><span data-stu-id="25464-162">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="25464-163">Но создавать этот номер не входит в обязанности вызывающего.</span><span class="sxs-lookup"><span data-stu-id="25464-163">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="25464-164">Код класса `BankAccount` должен иметь информацию о том, как присвоить номера новым счетам.</span><span class="sxs-lookup"><span data-stu-id="25464-164">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="25464-165">Проще всего начать с 10-значного числа.</span><span class="sxs-lookup"><span data-stu-id="25464-165">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="25464-166">Увеличивайте его при создании каждого нового счета.</span><span class="sxs-lookup"><span data-stu-id="25464-166">Increment it when each new account is created.</span></span> <span data-ttu-id="25464-167">Затем при создании объекта сохраните номер текущего счета.</span><span class="sxs-lookup"><span data-stu-id="25464-167">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="25464-168">Добавьте в класс `BankAccount` объявление члена.</span><span class="sxs-lookup"><span data-stu-id="25464-168">Add a member declaration to the `BankAccount` class.</span></span> <span data-ttu-id="25464-169">Поместите следующую строку кода после открывающей скобки `{` в начале класса `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="25464-169">Place the following line of code after the opening brace `{` at the beginning of the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="25464-170">Это элемент данных.</span><span class="sxs-lookup"><span data-stu-id="25464-170">This is a data member.</span></span> <span data-ttu-id="25464-171">Он имеет свойство `private`, то есть к нему может получить доступ только код внутри класса `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="25464-171">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="25464-172">Таким образом общедоступные обязательства (например, получение номера счета) отделяются от закрытой реализации (способ создания номеров счетов).</span><span class="sxs-lookup"><span data-stu-id="25464-172">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated).</span></span> <span data-ttu-id="25464-173">Также он является `static`, то есть совместно используется всеми объектами `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="25464-173">It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="25464-174">Значение нестатической переменной является уникальным для каждого экземпляра объекта `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="25464-174">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="25464-175">Добавьте две приведенные ниже строки в конструктор, чтобы назначить номер счета.</span><span class="sxs-lookup"><span data-stu-id="25464-175">Add the following two lines to the constructor to assign the account number.</span></span> <span data-ttu-id="25464-176">Они должны располагаться за строкой с текстом `this.Balance = initialBalance`.</span><span class="sxs-lookup"><span data-stu-id="25464-176">Place them after the line that says `this.Balance = initialBalance`:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="25464-177">Введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="25464-177">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="25464-178">Создание депозитов и списаний</span><span class="sxs-lookup"><span data-stu-id="25464-178">Create deposits and withdrawals</span></span>

<span data-ttu-id="25464-179">Для надлежащей работы ваш класс банковского счета должен принимать депозиты и списания.</span><span class="sxs-lookup"><span data-stu-id="25464-179">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="25464-180">Чтобы реализовать депозиты и списания, создадим журнал для каждой транзакции на счете.</span><span class="sxs-lookup"><span data-stu-id="25464-180">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="25464-181">Этот подход предпочтительнее, чем простое обновление сальдо после каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="25464-181">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="25464-182">Журнал можно использовать для аудита всех транзакций и управления ежедневным сальдо.</span><span class="sxs-lookup"><span data-stu-id="25464-182">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="25464-183">При необходимости можно вычислять сальдо с помощью журнала всех транзакций. Тогда при следующем вычислении все исправленные ошибки в одной транзакции будут правильно учтены в сальдо.</span><span class="sxs-lookup"><span data-stu-id="25464-183">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="25464-184">Начнем с создания нового типа, который представляет транзакцию.</span><span class="sxs-lookup"><span data-stu-id="25464-184">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="25464-185">Это простой тип без обязательств.</span><span class="sxs-lookup"><span data-stu-id="25464-185">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="25464-186">Ему нужно назначить несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="25464-186">It needs a few properties.</span></span> <span data-ttu-id="25464-187">Создайте новый файл с именем *Transaction.cs* .</span><span class="sxs-lookup"><span data-stu-id="25464-187">Create a new file named *Transaction.cs* .</span></span> <span data-ttu-id="25464-188">Добавьте в этот файл следующий код:</span><span class="sxs-lookup"><span data-stu-id="25464-188">Add the following code to it:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/Transaction.cs":::

<span data-ttu-id="25464-189">Теперь добавим <xref:System.Collections.Generic.List%601> объектов `Transaction` в класс `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="25464-189">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="25464-190">Добавьте следующее объявление после конструктора в файл *BankAccount.cs* :</span><span class="sxs-lookup"><span data-stu-id="25464-190">Add the following declaration after the constructor in your *BankAccount.cs* file:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="TransactionDeclaration":::

<span data-ttu-id="25464-191">Класс <xref:System.Collections.Generic.List%601> требует импортировать другое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="25464-191">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="25464-192">Добавьте следующий код в начало файла *BankAccount.cs* :</span><span class="sxs-lookup"><span data-stu-id="25464-192">Add the following at the beginning of *BankAccount.cs* :</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="25464-193">Далее мы соответствующим образом вычислим `Balance`.</span><span class="sxs-lookup"><span data-stu-id="25464-193">Now, let's correctly compute the `Balance`.</span></span> <span data-ttu-id="25464-194">Чтобы вычислить текущий баланс, нужно суммировать значения всех транзакций.</span><span class="sxs-lookup"><span data-stu-id="25464-194">The current balance can be found by summing the values of all transactions.</span></span> <span data-ttu-id="25464-195">В этом виде этот код позволяет получить только начальный баланс счета, поэтому необходимо обновить свойство `Balance`.</span><span class="sxs-lookup"><span data-stu-id="25464-195">As the code is currently, you can only get the initial balance of the account, so you'll have to update the `Balance` property.</span></span> <span data-ttu-id="25464-196">В файле *BankAccount.cs* замените строку `public decimal Balance { get; }` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="25464-196">Replace the line `public decimal Balance { get; }` in *BankAccount.cs* with the following code:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="BalanceComputation":::

<span data-ttu-id="25464-197">В этом примере показан важный аспект \* **свойств** _.</span><span class="sxs-lookup"><span data-stu-id="25464-197">This example shows an important aspect of \* **properties** _.</span></span> <span data-ttu-id="25464-198">Вы вычисляете сальдо, когда другой программист запрашивает значение.</span><span class="sxs-lookup"><span data-stu-id="25464-198">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="25464-199">В результате вашего вычисления выводится список всех транзакций и сумма в виде текущего сальдо.</span><span class="sxs-lookup"><span data-stu-id="25464-199">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="25464-200">Теперь реализуйте методы `MakeDeposit` и `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="25464-200">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="25464-201">Эти методы будут выполнять два последних правила: начальное сальдо должно быть положительным, списание не должно создавать отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="25464-201">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span>

<span data-ttu-id="25464-202">Это действие вводит понятие _\*_исключений_\*_ .</span><span class="sxs-lookup"><span data-stu-id="25464-202">This introduces the concept of _*_exceptions_*_ .</span></span> <span data-ttu-id="25464-203">Чтобы определить, что метод не может выполнить свою функцию, обычно вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="25464-203">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="25464-204">В типе исключения и связанном с ним сообщении описывается ошибка.</span><span class="sxs-lookup"><span data-stu-id="25464-204">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="25464-205">В этом примере метод `MakeDeposit` вызывает исключение, если сумма депозита является отрицательной.</span><span class="sxs-lookup"><span data-stu-id="25464-205">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="25464-206">Метод `MakeWithdrawal` вызывает исключение, если сумма списания является отрицательной или если при списании создается отрицательное сальдо.</span><span class="sxs-lookup"><span data-stu-id="25464-206">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance.</span></span> <span data-ttu-id="25464-207">Добавьте следующий код после объявления списка `allTransactions`:</span><span class="sxs-lookup"><span data-stu-id="25464-207">Add the following code after the declaration of the `allTransactions` list:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="DepositAndWithdrawal":::

<span data-ttu-id="25464-208">Инструкция [`throw`](../../language-reference/keywords/throw.md) _ *вызывает* \* исключение.</span><span class="sxs-lookup"><span data-stu-id="25464-208">The [`throw`](../../language-reference/keywords/throw.md) statement _ *throws* \* an exception.</span></span> <span data-ttu-id="25464-209">Выполнение текущего блока завершается и управление передается в первый подходящий блок `catch` из стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="25464-209">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="25464-210">Вы добавите блок `catch` для тестирования этого кода немного позже.</span><span class="sxs-lookup"><span data-stu-id="25464-210">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="25464-211">Чтобы вместо непосредственного обновления сальдо добавлялась начальная транзакция, конструктор должен получить одно изменение.</span><span class="sxs-lookup"><span data-stu-id="25464-211">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="25464-212">Так как вы уже написали метод `MakeDeposit`, вызовите его из конструктора.</span><span class="sxs-lookup"><span data-stu-id="25464-212">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="25464-213">Готовый конструктор должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="25464-213">The finished constructor should look like this:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="Constructor":::

<span data-ttu-id="25464-214"><xref:System.DateTime.Now?displayProperty=nameWithType> — это свойство, которое возвращает текущие дату и время.</span><span class="sxs-lookup"><span data-stu-id="25464-214"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="25464-215">Проверьте его. Для этого добавьте несколько депозитов и списаний в метод `Main` после кода, с помощью которого создается `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="25464-215">Test this by adding a few deposits and withdrawals in your `Main` method, following the code that creates a new `BankAccount`:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="25464-216">Теперь убедитесь, что условия возникновения ошибки срабатывают правильно, создав счет с отрицательным сальдо.</span><span class="sxs-lookup"><span data-stu-id="25464-216">Next, test that you are catching error conditions by trying to create an account with a negative balance.</span></span> <span data-ttu-id="25464-217">Добавьте следующий код после только что добавленного блока кода:</span><span class="sxs-lookup"><span data-stu-id="25464-217">Add the following code after the preceding code you just added:</span></span>

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

<span data-ttu-id="25464-218">С помощью [инструкций `try` и `catch`](../../language-reference/keywords/try-catch.md) пометьте блок кода, который может вызывать исключения, и перехватывайте ожидаемые сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="25464-218">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="25464-219">Так же можно проверять код, который вызывает исключение при получении отрицательного баланса.</span><span class="sxs-lookup"><span data-stu-id="25464-219">You can use the same technique to test the code that throws an exception for a negative balance.</span></span> <span data-ttu-id="25464-220">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="25464-220">Add the following code at the end of your `Main` method:</span></span>

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

<span data-ttu-id="25464-221">Сохраните файл и введите `dotnet run` для проверки.</span><span class="sxs-lookup"><span data-stu-id="25464-221">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="25464-222">Задача — регистрация всех транзакций</span><span class="sxs-lookup"><span data-stu-id="25464-222">Challenge - log all transactions</span></span>

<span data-ttu-id="25464-223">В завершение вы создадите метод `GetAccountHistory`, который создает `string` для журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="25464-223">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="25464-224">Добавьте этот метод в тип `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="25464-224">Add this method to the `BankAccount` type:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="History":::

<span data-ttu-id="25464-225">В этом примере используется класс <xref:System.Text.StringBuilder>, чтобы отформатировать строку, которая содержит одну строку для каждой транзакции.</span><span class="sxs-lookup"><span data-stu-id="25464-225">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="25464-226">Код форматирования строки вы уже видели в этой серии руководств.</span><span class="sxs-lookup"><span data-stu-id="25464-226">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="25464-227">В этом коде есть новый символ `\t`.</span><span class="sxs-lookup"><span data-stu-id="25464-227">One new character is `\t`.</span></span> <span data-ttu-id="25464-228">Он позволяет вставить вкладку для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="25464-228">That inserts a tab to format the output.</span></span>

<span data-ttu-id="25464-229">Добавьте следующую строку, чтобы проверить его в файле *Program.cs* :</span><span class="sxs-lookup"><span data-stu-id="25464-229">Add this line to test it in *Program.cs* :</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="25464-230">Снова выполните программу, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="25464-230">Run your program to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="25464-231">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="25464-231">Next steps</span></span>

<span data-ttu-id="25464-232">Если у вас возникли проблемы, изучите исходный код для этого руководства, размещенный [в репозитории GitHub](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes).</span><span class="sxs-lookup"><span data-stu-id="25464-232">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes).</span></span>

<span data-ttu-id="25464-233">Вы можете продолжить, перейдя к учебнику по [объектно-ориентированному программированию](object-oriented-programming.md).</span><span class="sxs-lookup"><span data-stu-id="25464-233">You can continue with the [object oriented programming](object-oriented-programming.md) tutorial.</span></span>

<span data-ttu-id="25464-234">Дополнительные сведения об этих понятиях см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="25464-234">You can learn more about these concepts in these articles:</span></span>

- [<span data-ttu-id="25464-235">if-else (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="25464-235">If and else statement</span></span>](../../language-reference/keywords/if-else.md)
- [<span data-ttu-id="25464-236">while (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="25464-236">While statement</span></span>](../../language-reference/keywords/while.md)
- [<span data-ttu-id="25464-237">do (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="25464-237">Do statement</span></span>](../../language-reference/keywords/do.md)
- [<span data-ttu-id="25464-238">for (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="25464-238">For statement</span></span>](../../language-reference/keywords/for.md)
