---
title: Получите образцы баз данных S'L Server для ADO.NET образцов кода
description: Загрузите образцы баз данных S'L Server, используемые в образцах кода в документации ADO.NET, а также инструменты s'L Server и управления
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 3449f502834f449f5023bd52457d45ffaf9b0fa1
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607988"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="14035-103">Получить образцы баз данных для образцов кода ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14035-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="14035-104">В ряде примеров и пошагов в документации [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] используются образцы баз данных сервера S'L ИС ИСИ И.</span><span class="sxs-lookup"><span data-stu-id="14035-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="14035-105">Вы можете скачать эти продукты бесплатно от Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14035-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="14035-106">Получение выборочной базы данных Northwind для сервера S'L</span><span class="sxs-lookup"><span data-stu-id="14035-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="14035-107">Загрузите `instnwnd.sql` скрипт из следующего репозитория GitHub для создания и загрузки выборочной базы данных Northwind для сервера S'L:</span><span class="sxs-lookup"><span data-stu-id="14035-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="14035-108">Нортвинд и пабы образцы баз данных для Microsoft S'L Server</span><span class="sxs-lookup"><span data-stu-id="14035-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="14035-109">Прежде чем использовать базу данных Northwind, необходимо `instnwnd.sql` запустить загруженный файл скрипта, чтобы воссоздать базу данных на экземпляре сервера S'L, используя [студию управления серверами S'L](#get_ssms) или аналогичный инструмент.</span><span class="sxs-lookup"><span data-stu-id="14035-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="14035-110">Следуйте инструкциям в файле Readme в репозитории.</span><span class="sxs-lookup"><span data-stu-id="14035-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="14035-111">Если вы ищете базу данных Northwind для Microsoft Access, [см.](#northwind_access)</span><span class="sxs-lookup"><span data-stu-id="14035-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a><span data-ttu-id="14035-112">Получить образец базы данных Northwind для Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="14035-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="14035-113">Образная база данных Northwind для Microsoft Access недоступна в Центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="14035-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="14035-114">Чтобы установить Northwind непосредственно из Access, сделайте следующие вещи:</span><span class="sxs-lookup"><span data-stu-id="14035-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="14035-115">Открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="14035-115">Open Access.</span></span>

1. <span data-ttu-id="14035-116">Введите **Northwind** в поле **поиска онлайн шаблонов,** а затем выберите **Enter.**</span><span class="sxs-lookup"><span data-stu-id="14035-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="14035-117">На экране результатов выберите **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="14035-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="14035-118">Новое окно открывается с описанием базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="14035-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="14035-119">В новом окне, в текстовом окне **имя файла,** укажите имя файла для вашей копии базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="14035-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="14035-120">Нажмите кнопку **создания**.</span><span class="sxs-lookup"><span data-stu-id="14035-120">Select **Create**.</span></span> <span data-ttu-id="14035-121">Access загружает базу данных Northwind и готовит файл.</span><span class="sxs-lookup"><span data-stu-id="14035-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="14035-122">Когда этот процесс завершен, база данных открывается с экрана Welcome.</span><span class="sxs-lookup"><span data-stu-id="14035-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="14035-123">Получить образец базы данных AdventureWorks для сервера S'L</span><span class="sxs-lookup"><span data-stu-id="14035-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="14035-124">Загрузите образец базы данных AdventureWorks для сервера S'L из следующего репозитория GitHub:</span><span class="sxs-lookup"><span data-stu-id="14035-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="14035-125">Образцы баз данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="14035-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="14035-126">После загрузки одного из файлов\*резервного копирования базы данных (.bak) восстановите резервную часть в экземпляре сервера S'L, используя s'L Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="14035-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="14035-127">Подробнее о [том, как получить студию управления серверами S'L](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="14035-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a><span data-ttu-id="14035-128">Получите студию управления серверами S'L</span><span class="sxs-lookup"><span data-stu-id="14035-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="14035-129">Если вы хотите просмотреть или изменить загруженную базу данных, вы можете использовать студию управления серверами S'L (SSMS).</span><span class="sxs-lookup"><span data-stu-id="14035-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="14035-130">Скачать SSMS со следующей страницы:</span><span class="sxs-lookup"><span data-stu-id="14035-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="14035-131">Скачивание SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="14035-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="14035-132">Вы также можете просматривать и управлять базами данных в интегрированной среде разработки Visual Studio (IDE).</span><span class="sxs-lookup"><span data-stu-id="14035-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="14035-133">В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)подключитесь к базе данных из **S'L Server Object Explorer**или создайте подключение к базе данных в Server **Explorer.**</span><span class="sxs-lookup"><span data-stu-id="14035-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="14035-134">Откройте эти панели исследователей из меню **View.**</span><span class="sxs-lookup"><span data-stu-id="14035-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a><span data-ttu-id="14035-135">Получить сервер экспресс S'L</span><span class="sxs-lookup"><span data-stu-id="14035-135">Get SQL Server Express</span></span>

<span data-ttu-id="14035-136">S'L Server Express — это бесплатное издание сервера начального уровня, которое можно перераспределить с помощью приложений.</span><span class="sxs-lookup"><span data-stu-id="14035-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="14035-137">Скачать серверный экспресс s'L со следующей страницы:</span><span class="sxs-lookup"><span data-stu-id="14035-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="14035-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="14035-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="14035-139">Если вы используете [Visual Studio,](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)S'L Server Express LocalDB включен в бесплатное издание Сообщества Visual Studio, а также профессиональные и более высокие издания.</span><span class="sxs-lookup"><span data-stu-id="14035-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="14035-140">См. также</span><span class="sxs-lookup"><span data-stu-id="14035-140">See also</span></span>

- [<span data-ttu-id="14035-141">Начало работы</span><span class="sxs-lookup"><span data-stu-id="14035-141">Getting Started</span></span>](getting-started.md)
