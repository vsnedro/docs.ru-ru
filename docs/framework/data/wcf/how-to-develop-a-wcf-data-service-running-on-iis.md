---
title: Практическое руководство. Разработка службы данных WCF Data Service, работающей на IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: 8a1a0c2c55267940463e2c9ab82bb52345269260
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121615"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="0b7b7-102">Как: Разработка службы данных WCF, работая на IIS</span><span class="sxs-lookup"><span data-stu-id="0b7b7-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="0b7b7-103">В этой статье показано, как использовать WCF Data Services для создания службы данных, основанной на выборочной базе данных Northwind, размещенной ASP.NET веб-приложением, работающим на Информационных службах Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="0b7b7-103">This article shows how to use WCF Data Services to create a data service that's based on the Northwind sample database that's hosted by an ASP.NET Web app running on Internet Information Services (IIS).</span></span> <span data-ttu-id="0b7b7-104">Пример того, как создать тот же сервис данных Northwind, что и веб-приложение ASP.NET, которое работает на сервере разработки ASP.NET, [см.](quickstart-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="0b7b7-104">For an example of how to create the same Northwind data service as an ASP.NET Web app that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0b7b7-105">Для создания службы данных Northwind сначала установите образец базы данных Northwind на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-105">To create the Northwind data service, first install the Northwind sample database on the local computer.</span></span> <span data-ttu-id="0b7b7-106">Для установки базы данных запустите скрипт Transact-S'L из [баз данных Northwind и пабов для Microsoft S'L Server.](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)</span><span class="sxs-lookup"><span data-stu-id="0b7b7-106">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

<span data-ttu-id="0b7b7-107">В этой статье показано, как создать службу данных с помощью поставщика Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-107">This article shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="0b7b7-108">Доступны другие поставщики служб данных.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-108">Other data services providers are available.</span></span> <span data-ttu-id="0b7b7-109">Для получения дополнительной [информации см.](data-services-providers-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="0b7b7-109">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>

<span data-ttu-id="0b7b7-110">После создания службы требуется явно предоставить доступ к ресурсам службы данных.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="0b7b7-111">Для получения дополнительной информации [см.](how-to-enable-access-to-the-data-service-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="0b7b7-111">For more information, see [How to: Enable Access to the Data Service](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="0b7b7-112">Создание веб-приложения ASP.NET, которое работает на IIS</span><span class="sxs-lookup"><span data-stu-id="0b7b7-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="0b7b7-113">В Visual Studio в меню **Файл** выберите пункты **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="0b7b7-114">В диалоговом окне **нового проекта** выберите **«Установленную** >»**(Visual C)** или **«Visual Basic»**> **веб-категории.**</span><span class="sxs-lookup"><span data-stu-id="0b7b7-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="0b7b7-115">Выберите шаблон **Веб-приложение ASP.NET** .</span><span class="sxs-lookup"><span data-stu-id="0b7b7-115">Select the **ASP.NET Web Application** template.</span></span>

4. <span data-ttu-id="0b7b7-116">Введите `NorthwindService` как название проекта.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="0b7b7-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-117">Click **OK**.</span></span>

6. <span data-ttu-id="0b7b7-118">В меню **проекта** выберите **недвижимость NorthwindService.**</span><span class="sxs-lookup"><span data-stu-id="0b7b7-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="0b7b7-119">Выберите **web-вкладку,** а затем выберите **Используйте локальный веб-сервер IIS.**</span><span class="sxs-lookup"><span data-stu-id="0b7b7-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="0b7b7-120">Нажмите **Создать виртуальный каталог,** а затем нажмите **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="0b7b7-121">С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).</span><span class="sxs-lookup"><span data-stu-id="0b7b7-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="0b7b7-122">32-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="0b7b7-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - <span data-ttu-id="0b7b7-123">64-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="0b7b7-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="0b7b7-124">Она регистрирует Windows Communication Foundation (WCF) на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="0b7b7-125">С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).</span><span class="sxs-lookup"><span data-stu-id="0b7b7-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="0b7b7-126">32-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="0b7b7-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - <span data-ttu-id="0b7b7-127">64-разрядные системы:</span><span class="sxs-lookup"><span data-stu-id="0b7b7-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="0b7b7-128">Это необходимо для того, чтобы проверить правильность работы служб IIS после установки WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="0b7b7-129">Возможно, потребуется перезапустить службы IIS.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="0b7b7-130">Если приложение ASP.NET запущено в службах IIS7, нужно также выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="0b7b7-131">Откройте IIS Manager и перейдите к приложению PhotoService под **веб-узлом по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="0b7b7-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="0b7b7-132">В окне **Просмотр возможностей** дважды щелкните элемент **Проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="0b7b7-133">На странице **Проверка подлинности** выберите **Анонимная проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="0b7b7-134">В панели **действий** щелкните **Edit,** чтобы установить принцип безопасности, под которым анонимные пользователи будут подключаться к сайту.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="0b7b7-135">В диалоговом окне **учетных данных Edit Anonymous Authentication credentials** выберите **идентичуение пула приложений.**</span><span class="sxs-lookup"><span data-stu-id="0b7b7-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0b7b7-136">При использовании учетной записи сетевой службы анонимным пользователям предоставляется доступ к внутренней сети, связанной с этой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="0b7b7-137">С помощью среды SQL Server Management Studio, программы sqlcmd.exe или редактора Transact-SQL в Visual Studio выполните следующую команду Transact-SQL для экземпляра SQL Server с прикрепленной базой данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="0b7b7-138">Она создает имя входа в экземпляр SQL Server для учетной записи Windows, используемой для запуска служб IIS.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="0b7b7-139">Это позволит службам IIS подключиться к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="0b7b7-140">После присоединения базы данных Northwind выполните следующие команды Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="0b7b7-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    <span data-ttu-id="0b7b7-141">Они предоставляют право на новое имя входа, позволяющее службам IIS читать данные из базы данных Northwind и записывать данные в эту базу данных.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="0b7b7-142">Определение модели данных</span><span class="sxs-lookup"><span data-stu-id="0b7b7-142">Define the data model</span></span>

1. <span data-ttu-id="0b7b7-143">В **Solution Explorer**, правой кнопкой мыши имя ASP.NET проекта, а затем нажмите **Добавить** > **новый пункт**.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="0b7b7-144">В диалоговом окне **Добавить новый элемент** выберите **ADO.NET модель данных entity.**</span><span class="sxs-lookup"><span data-stu-id="0b7b7-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="0b7b7-145">Для названия модели данных `Northwind.edmx`введите тип .</span><span class="sxs-lookup"><span data-stu-id="0b7b7-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="0b7b7-146">В Волшебник модели данных Сущности выберите **Generate из базы данных,** а затем нажмите **далее**.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="0b7b7-147">Подключите модель данных к базе данных, выдвив один из следующих шагов, а затем нажмите **Далее:**</span><span class="sxs-lookup"><span data-stu-id="0b7b7-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="0b7b7-148">Если у вас нет уже настроенного соединения базы данных, нажмите **New Connection** и создайте новое соединение.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="0b7b7-149">Дополнительные сведения см. в разделе [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0b7b7-149">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="0b7b7-150">Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="0b7b7-151">\- или -</span><span class="sxs-lookup"><span data-stu-id="0b7b7-151">\- or -</span></span>

    - <span data-ttu-id="0b7b7-152">Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="0b7b7-153">На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="0b7b7-154">Чтобы завершить работу мастера, нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="0b7b7-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="0b7b7-155">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="0b7b7-155">Create the data service</span></span>

1. <span data-ttu-id="0b7b7-156">В **Solution Explorer**, правой кнопкой мыши имя вашего ASP.NET проекта, а затем нажмите **Добавить** > **новый пункт**.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="0b7b7-157">В диалоговом окне **Добавить новый элемент** выберите **службу данных WCF.**</span><span class="sxs-lookup"><span data-stu-id="0b7b7-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="0b7b7-159">Шаблон **WCF Data Service** доступен в Visual Studio 2015, но не в Visual Studio 2017 или позже.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="0b7b7-160">Для названия службы, `Northwind`введите .</span><span class="sxs-lookup"><span data-stu-id="0b7b7-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="0b7b7-161">В Visual Studio для новой службы создаются файлы разметки и кодов XML.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="0b7b7-162">По умолчанию открывается окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="0b7b7-163">В **Solution Explorer**служба имеет название, Northwind и расширение .svc.cs или .svc.vb.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="0b7b7-164">В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="0b7b7-165">Определение класса должно выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0b7b7-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="0b7b7-166">См. также</span><span class="sxs-lookup"><span data-stu-id="0b7b7-166">See also</span></span>

- [<span data-ttu-id="0b7b7-167">Предоставление данных как службы</span><span class="sxs-lookup"><span data-stu-id="0b7b7-167">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
