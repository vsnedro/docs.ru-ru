---
title: Пошаговое руководство. Простая модель объектов и простой запрос (C#)
description: Следуйте указаниям этого пошагового руководства, чтобы создать класс сущностей, моделирующий таблицу в образце базы данных. Затем создайте простой запрос для вывода списка клиентов в определенном расположении.
ms.date: 03/30/2017
ms.assetid: 419961cc-92d6-45f5-ae8a-d485bdde3a37
ms.openlocfilehash: 4637fabecc1726d8fec12857a667073912cfbed5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286305"
---
# <a name="walkthrough-simple-object-model-and-query-c"></a><span data-ttu-id="73c3a-104">Пошаговое руководство. Простая модель объектов и простой запрос (C#)</span><span class="sxs-lookup"><span data-stu-id="73c3a-104">Walkthrough: Simple Object Model and Query (C#)</span></span>

<span data-ttu-id="73c3a-105">В данном пошаговом руководстве представлен основной и полный сценарий [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] с подробным объяснением выполняемых действий.</span><span class="sxs-lookup"><span data-stu-id="73c3a-105">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="73c3a-106">В нем создается класс сущностей, который моделирует таблицу Customers в учебной базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="73c3a-106">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="73c3a-107">После этого создается простой запрос на получение списка клиентов, находящихся в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="73c3a-107">You will then create a simple query to list customers who are located in London.</span></span>

<span data-ttu-id="73c3a-108">Данное руководство ориентировано на создание кода, чтобы продемонстрировать основные понятия технологии [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73c3a-108">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="73c3a-109">Как правило, для создания объектной модели следует использовать реляционный конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="73c3a-109">Normally speaking, you would use the Object Relational Designer to create your object model.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="73c3a-110">Это пошаговое руководство было написано с использованием параметров разработки Visual C#.</span><span class="sxs-lookup"><span data-stu-id="73c3a-110">This walkthrough was written by using Visual C# Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73c3a-111">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="73c3a-111">Prerequisites</span></span>

- <span data-ttu-id="73c3a-112">Для хранения файлов используется выделенная папка ("c:\linqtest5").</span><span class="sxs-lookup"><span data-stu-id="73c3a-112">This walkthrough uses a dedicated folder ("c:\linqtest5") to hold files.</span></span> <span data-ttu-id="73c3a-113">Прежде чем приступить к выполнению задач, создайте такую папку.</span><span class="sxs-lookup"><span data-stu-id="73c3a-113">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="73c3a-114">В данном пошаговом руководстве требуется доступ к учебной базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="73c3a-114">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="73c3a-115">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="73c3a-115">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="73c3a-116">Инструкции см. в разделе [Загрузка образцов баз данных](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="73c3a-116">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="73c3a-117">После загрузки базы данных скопируйте файл в папку c:\linqtest5.</span><span class="sxs-lookup"><span data-stu-id="73c3a-117">After you have downloaded the database, copy the file to the c:\linqtest5 folder.</span></span>

## <a name="overview"></a><span data-ttu-id="73c3a-118">Обзор</span><span class="sxs-lookup"><span data-stu-id="73c3a-118">Overview</span></span>

<span data-ttu-id="73c3a-119">Данное пошаговое руководство состоит из шести основных задач.</span><span class="sxs-lookup"><span data-stu-id="73c3a-119">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="73c3a-120">Создание [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] решения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="73c3a-120">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="73c3a-121">Сопоставление класса с таблицей базы данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-121">Mapping a class to a database table.</span></span>

- <span data-ttu-id="73c3a-122">Назначение свойств классу для представления столбцов базы данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-122">Designating properties on the class to represent database columns.</span></span>

- <span data-ttu-id="73c3a-123">Указание подключения к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="73c3a-123">Specifying the connection to the Northwind database.</span></span>

- <span data-ttu-id="73c3a-124">Создание простого запроса к базе данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-124">Creating a simple query to run against the database.</span></span>

- <span data-ttu-id="73c3a-125">Выполнение запроса и просмотр результатов.</span><span class="sxs-lookup"><span data-stu-id="73c3a-125">Executing the query and observing the results.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="73c3a-126">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="73c3a-126">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="73c3a-127">В этой первой задаче вы создадите решение Visual Studio, содержащее необходимые ссылки для сборки и запуска [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="73c3a-127">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="73c3a-128">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="73c3a-128">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="73c3a-129">В меню **файл** Visual Studio наведите указатель на пункт **создать**и выберите пункт **проект**.</span><span class="sxs-lookup"><span data-stu-id="73c3a-129">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="73c3a-130">На панели **типы проектов** диалогового окна **Новый проект** щелкните **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="73c3a-130">In the **Project types** pane of the **New Project** dialog box, click **Visual C#**.</span></span>

3. <span data-ttu-id="73c3a-131">В области **Шаблоны** щелкните **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="73c3a-131">In the **Templates** pane, click **Console Application**.</span></span>

4. <span data-ttu-id="73c3a-132">В поле **имя** введите **линкконсолеапп**.</span><span class="sxs-lookup"><span data-stu-id="73c3a-132">In the **Name** box, type **LinqConsoleApp**.</span></span>

5. <span data-ttu-id="73c3a-133">В поле **Расположение** проверьте, где вы хотите сохранить файлы проекта.</span><span class="sxs-lookup"><span data-stu-id="73c3a-133">In the **Location** box, verify where you want to store your project files.</span></span>

6. <span data-ttu-id="73c3a-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="73c3a-134">Click **OK**.</span></span>

## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="73c3a-135">Добавление ссылок и директив LINQ</span><span class="sxs-lookup"><span data-stu-id="73c3a-135">Adding LINQ References and Directives</span></span>

<span data-ttu-id="73c3a-136">В этом пошаговом руководстве используются сборки, которые могут быть не установлены по умолчанию в проект.</span><span class="sxs-lookup"><span data-stu-id="73c3a-136">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="73c3a-137">Если System. Data. LINQ не указан в качестве ссылки в проекте (разверните узел **ссылки** в **Обозреватель решений**), добавьте его, как описано в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="73c3a-137">If System.Data.Linq is not listed as a reference in your project (expand the **References** node in **Solution Explorer**), add it, as explained in the following steps.</span></span>

### <a name="to-add-systemdatalinq"></a><span data-ttu-id="73c3a-138">Добавление сборки System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="73c3a-138">To add System.Data.Linq</span></span>

1. <span data-ttu-id="73c3a-139">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **ссылки**и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="73c3a-139">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="73c3a-140">В диалоговом окне **Добавление ссылки** щелкните **.NET**, выберите сборку System. Data. LINQ и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="73c3a-140">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="73c3a-141">Сборка будет добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="73c3a-141">The assembly is added to the project.</span></span>

3. <span data-ttu-id="73c3a-142">Добавьте следующие директивы в начало **Program.CS**:</span><span class="sxs-lookup"><span data-stu-id="73c3a-142">Add the following directives at the top of **Program.cs**:</span></span>

     [!code-csharp[DLinqWalk1CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#1)]

## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="73c3a-143">Сопоставление класса с таблицей базы данных</span><span class="sxs-lookup"><span data-stu-id="73c3a-143">Mapping a Class to a Database Table</span></span>

<span data-ttu-id="73c3a-144">На этом этапе создается класс, который сопоставляется с таблицей базы данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-144">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="73c3a-145">Такой класс называется *классом сущностей*.</span><span class="sxs-lookup"><span data-stu-id="73c3a-145">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="73c3a-146">Обратите внимание, что сопоставление осуществляется простым добавлением атрибута <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="73c3a-146">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="73c3a-147">Свойство <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> задает имя таблицы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-147">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>

### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="73c3a-148">Создание класса сущностей и его сопоставление с таблицей базы данных</span><span class="sxs-lookup"><span data-stu-id="73c3a-148">To create an entity class and map it to a database table</span></span>

- <span data-ttu-id="73c3a-149">Введите или вставьте следующий код в Program.cs непосредственно перед объявлением класса `Program`.</span><span class="sxs-lookup"><span data-stu-id="73c3a-149">Type or paste the following code into Program.cs immediately above the `Program` class declaration:</span></span>

     [!code-csharp[DLinqWalk1CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#2)]

## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="73c3a-150">Назначение свойств классу для представления столбцов базы данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-150">Designating Properties on the Class to Represent Database Columns</span></span>

<span data-ttu-id="73c3a-151">На этом этапе выполняется несколько задач.</span><span class="sxs-lookup"><span data-stu-id="73c3a-151">In this step, you accomplish several tasks.</span></span>

- <span data-ttu-id="73c3a-152">Используется атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute> для назначения классу сущностей свойств `CustomerID` и `City`, представляющих столбцы в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-152">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>

- <span data-ttu-id="73c3a-153">Назначается свойство `CustomerID`, представляющее столбец первичного ключа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-153">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>

- <span data-ttu-id="73c3a-154">Назначаются поля `_CustomerID` и `_City` для закрытого хранения.</span><span class="sxs-lookup"><span data-stu-id="73c3a-154">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="73c3a-155">После этого [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сможет напрямую сохранять и извлекать значения, вместо вызова открытых методов доступа, которые могут содержать бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="73c3a-155">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>

### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="73c3a-156">Представление характеристик двух столбцов базы данных</span><span class="sxs-lookup"><span data-stu-id="73c3a-156">To represent characteristics of two database columns</span></span>

- <span data-ttu-id="73c3a-157">Для класса `Customer` введите или вставьте следующий код в Program.cs в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="73c3a-157">Type or paste the following code into Program.cs inside the curly braces for the `Customer` class.</span></span>

     [!code-csharp[DLinqWalk1CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#3)]

## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="73c3a-158">Указание подключения к базе данных Northwind</span><span class="sxs-lookup"><span data-stu-id="73c3a-158">Specifying the Connection to the Northwind Database</span></span>

<span data-ttu-id="73c3a-159">На этом этапе для установки подключения между основанными на коде структурами данных и самой базой данных используется объект <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="73c3a-159">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="73c3a-160">Основным каналом, через который извлекаются объекты из базы данных и отправляются изменения, является класс <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="73c3a-160">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>

<span data-ttu-id="73c3a-161">Также объявляется объект `Table<Customer>`, который действует как логическая типизированная таблица для запросов к таблице Customers в базе данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-161">You also declare a `Table<Customer>` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="73c3a-162">Эти запросы создаются и выполняются в последующих действиях.</span><span class="sxs-lookup"><span data-stu-id="73c3a-162">You will create and execute these queries in later steps.</span></span>

### <a name="to-specify-the-database-connection"></a><span data-ttu-id="73c3a-163">Указание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="73c3a-163">To specify the database connection</span></span>

- <span data-ttu-id="73c3a-164">Введите или вставьте следующий код в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="73c3a-164">Type or paste the following code into the `Main` method.</span></span>

     <span data-ttu-id="73c3a-165">Обратите внимание, что файл `northwnd.mdf` находится в папке "linqtest5".</span><span class="sxs-lookup"><span data-stu-id="73c3a-165">Note that the `northwnd.mdf` file is assumed to be in the linqtest5 folder.</span></span> <span data-ttu-id="73c3a-166">Дополнительные сведения см. в разделе "Предварительные требования" ранее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="73c3a-166">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

     [!code-csharp[DLinqWalk1CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#4)]

## <a name="creating-a-simple-query"></a><span data-ttu-id="73c3a-167">Создание простого запроса</span><span class="sxs-lookup"><span data-stu-id="73c3a-167">Creating a Simple Query</span></span>

<span data-ttu-id="73c3a-168">На этом этапе создается запрос для поиска клиентов из таблицы Customers базы данных, находящихся в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="73c3a-168">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="73c3a-169">Код запроса, создаваемый на этом шаге, только описывает запрос.</span><span class="sxs-lookup"><span data-stu-id="73c3a-169">The query code in this step just describes the query.</span></span> <span data-ttu-id="73c3a-170">но не выполняет его.</span><span class="sxs-lookup"><span data-stu-id="73c3a-170">It does not execute it.</span></span> <span data-ttu-id="73c3a-171">Этот подход называется *отложенным выполнением*.</span><span class="sxs-lookup"><span data-stu-id="73c3a-171">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="73c3a-172">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="73c3a-172">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

<span data-ttu-id="73c3a-173">Можно также записать выходные данные в журнал, чтобы продемонстрировать команды SQL, создаваемые технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73c3a-173">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="73c3a-174">Возможность ведения журнала (которая использует метод <xref:System.Data.Linq.DataContext.Log%2A>) очень полезна при отладке, а также при проверке того, что команды, отправляемые в базу данных, точно соответствуют запросу.</span><span class="sxs-lookup"><span data-stu-id="73c3a-174">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="73c3a-175">Создание простого запроса</span><span class="sxs-lookup"><span data-stu-id="73c3a-175">To create a simple query</span></span>

- <span data-ttu-id="73c3a-176">Введите или вставьте следующий код в метод `Main` после объявления `Table<Customer>`.</span><span class="sxs-lookup"><span data-stu-id="73c3a-176">Type or paste the following code into the `Main` method after the `Table<Customer>` declaration.</span></span>

     [!code-csharp[DLinqWalk1ACS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#5)]

## <a name="executing-the-query"></a><span data-ttu-id="73c3a-177">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="73c3a-177">Executing the Query</span></span>

<span data-ttu-id="73c3a-178">На этом шаге производится фактическое выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="73c3a-178">In this step, you actually execute the query.</span></span> <span data-ttu-id="73c3a-179">Выражения запроса, созданные на предыдущем этапе, не оцениваются до тех пор, пока не понадобятся результаты.</span><span class="sxs-lookup"><span data-stu-id="73c3a-179">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="73c3a-180">После начала итерации `foreach` выполняется команда SQL для базы данных и материализуются объекты.</span><span class="sxs-lookup"><span data-stu-id="73c3a-180">When you begin the `foreach` iteration, a SQL command is executed against the database and objects are materialized.</span></span>

### <a name="to-execute-the-query"></a><span data-ttu-id="73c3a-181">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="73c3a-181">To execute the query</span></span>

1. <span data-ttu-id="73c3a-182">Введите или вставьте следующий код в конце метода `Main` (после описания запроса).</span><span class="sxs-lookup"><span data-stu-id="73c3a-182">Type or paste the following code at the end of the `Main` method (after the query description).</span></span>

     [!code-csharp[DLinqWalk1ACS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#6)]

2. <span data-ttu-id="73c3a-183">Нажмите клавишу F5, чтобы начать отладку приложения.</span><span class="sxs-lookup"><span data-stu-id="73c3a-183">Press F5 to debug the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="73c3a-184">Если приложение создает ошибку во время выполнения, см. [Пошаговые руководства](learning-by-walkthroughs.md)в разделе Устранение неполадок.</span><span class="sxs-lookup"><span data-stu-id="73c3a-184">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

     <span data-ttu-id="73c3a-185">В окне консоли отображаются следующие результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="73c3a-185">The query results in the console window should appear as follows:</span></span>

     `ID=AROUT, City=London`

     `ID=BSBEV, City=London`

     `ID=CONSH, City=London`

     `ID=EASTC, City=London`

     `ID=NORTS, City=London`

     `ID=SEVES, City=London`

3. <span data-ttu-id="73c3a-186">Чтобы закрыть приложение, в окне консоли нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="73c3a-186">Press Enter in the console window to close the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="73c3a-187">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="73c3a-187">Next Steps</span></span>

<span data-ttu-id="73c3a-188">В разделе [Пошаговое руководство. запросы по связям (C#)](walkthrough-querying-across-relationships-csharp.md) будет показано, где заканчивается это пошаговое руководство.</span><span class="sxs-lookup"><span data-stu-id="73c3a-188">The [Walkthrough: Querying Across Relationships (C#)](walkthrough-querying-across-relationships-csharp.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="73c3a-189">В пошаговом руководстве запрос по связям показано [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , как можно выполнять запросы к нескольким таблицам, как и к *объединениям* в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="73c3a-189">The Query Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>

<span data-ttu-id="73c3a-190">Если требуется выполнить пошаговое руководство "Выполнение запросов в связях", необходимо сохранить решение, созданное в процессе только что завершенного пошагового руководства. Это условие является обязательным.</span><span class="sxs-lookup"><span data-stu-id="73c3a-190">If you want to do the Query Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>

## <a name="see-also"></a><span data-ttu-id="73c3a-191">См. также</span><span class="sxs-lookup"><span data-stu-id="73c3a-191">See also</span></span>

- [<span data-ttu-id="73c3a-192">Обучение с использованием пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="73c3a-192">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
