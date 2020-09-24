---
title: Получение образца SQL Server баз данных для примеров кода ADO.NET
description: Скачайте пример SQL Server баз данных, используемых в примерах кода в документации по ADO.NET, а также SQL Server и средств управления.
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: f7c0d1eb0089a6bfabc92e1deecf563c3e59cc6a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156060"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="9a248-103">Получение образцов баз данных для примеров кода ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9a248-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="9a248-104">Некоторые примеры и пошаговые руководства в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации используют пример SQL Server баз данных и SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="9a248-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="9a248-105">Эти продукты можно бесплатно загрузить с веб – Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9a248-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="9a248-106">Получение образца базы данных Northwind для SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a248-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="9a248-107">Скачайте скрипт `instnwnd.sql` из следующего репозитория GitHub, чтобы создать и загрузить образец базы данных Northwind для SQL Server:</span><span class="sxs-lookup"><span data-stu-id="9a248-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="9a248-108">Учебные базы данных Northwind и Pubs для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a248-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="9a248-109">Прежде чем можно будет использовать базу данных Northwind, необходимо запустить скачанный `instnwnd.sql` файл скрипта, чтобы повторно создать базу данных на экземпляре SQL Server с помощью [SQL Server Management Studio](#get_ssms) или аналогичного средства.</span><span class="sxs-lookup"><span data-stu-id="9a248-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="9a248-110">Следуйте инструкциям в файле сведений в репозитории.</span><span class="sxs-lookup"><span data-stu-id="9a248-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="9a248-111">Если вы ищете базу данных Northwind для Microsoft Access, см. статью [Установка образца базы данных Northwind для Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="9a248-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a> <span data-ttu-id="9a248-112">Получение образца базы данных Northwind для Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="9a248-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="9a248-113">Образец базы данных Northwind для Microsoft Access недоступен в центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9a248-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="9a248-114">Чтобы установить Northwind непосредственно из Access, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9a248-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="9a248-115">Откройте Access.</span><span class="sxs-lookup"><span data-stu-id="9a248-115">Open Access.</span></span>

1. <span data-ttu-id="9a248-116">В поле **Поиск шаблонов в Интернете** введите **Northwind** , а затем нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="9a248-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="9a248-117">На экране результатов выберите **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="9a248-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="9a248-118">Откроется новое окно с описанием базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="9a248-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="9a248-119">В новом окне в текстовом поле **имя файла** укажите имя файла для копии базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="9a248-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="9a248-120">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9a248-120">Select **Create**.</span></span> <span data-ttu-id="9a248-121">Access загружает базу данных Northwind и готовит файл.</span><span class="sxs-lookup"><span data-stu-id="9a248-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="9a248-122">После завершения этого процесса база данных откроется с экраном приветствия.</span><span class="sxs-lookup"><span data-stu-id="9a248-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="9a248-123">Получение образца базы данных AdventureWorks для SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a248-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="9a248-124">Скачайте образец базы данных AdventureWorks для SQL Server из следующего репозитория GitHub:</span><span class="sxs-lookup"><span data-stu-id="9a248-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="9a248-125">Образцы баз данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="9a248-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="9a248-126">После загрузки одного из файлов резервной копии базы данных ( \* bak) восстановите резервную копию на экземпляре SQL Server с помощью SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="9a248-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="9a248-127">См. раздел [Get SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="9a248-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a> <span data-ttu-id="9a248-128">Получить SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a248-128">Get SQL Server Management Studio</span></span>

<span data-ttu-id="9a248-129">Если вы хотите просмотреть или изменить загруженную базу данных, можно использовать SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="9a248-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="9a248-130">Скачайте среду SSMS со следующей страницы:</span><span class="sxs-lookup"><span data-stu-id="9a248-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="9a248-131">Скачивание SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="9a248-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="9a248-132">Вы также можете просматривать базы данных и управлять ими в интегрированной среде разработки Visual Studio (IDE).</span><span class="sxs-lookup"><span data-stu-id="9a248-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="9a248-133">В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)подключитесь к базе данных из **Обозреватель объектов SQL Server**или создайте подключение к базе данных в **Обозреватель сервера**.</span><span class="sxs-lookup"><span data-stu-id="9a248-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="9a248-134">Откройте эти панели обозревателя в меню **вид** .</span><span class="sxs-lookup"><span data-stu-id="9a248-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a> <span data-ttu-id="9a248-135">Получить SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="9a248-135">Get SQL Server Express</span></span>

<span data-ttu-id="9a248-136">SQL Server Express — это бесплатный выпуск SQL Server, который можно распространять вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="9a248-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="9a248-137">Скачайте SQL Server Express со следующей страницы:</span><span class="sxs-lookup"><span data-stu-id="9a248-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="9a248-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="9a248-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="9a248-139">Если вы используете [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB входит в бесплатный выпуск сообщества Visual Studio, а также в профессиональный и более поздние версии.</span><span class="sxs-lookup"><span data-stu-id="9a248-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9a248-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9a248-140">See also</span></span>

- [<span data-ttu-id="9a248-141">Начало работы</span><span class="sxs-lookup"><span data-stu-id="9a248-141">Getting Started</span></span>](getting-started.md)
