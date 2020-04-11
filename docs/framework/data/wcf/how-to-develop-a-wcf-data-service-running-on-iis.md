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
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Как: Разработка службы данных WCF, работая на IIS

В этой статье показано, как использовать WCF Data Services для создания службы данных, основанной на выборочной базе данных Northwind, размещенной ASP.NET веб-приложением, работающим на Информационных службах Интернета (IIS). Пример того, как создать тот же сервис данных Northwind, что и веб-приложение ASP.NET, которое работает на сервере разработки ASP.NET, [см.](quickstart-wcf-data-services.md)

> [!NOTE]
> Для создания службы данных Northwind сначала установите образец базы данных Northwind на локальном компьютере. Для установки базы данных запустите скрипт Transact-S'L из [баз данных Northwind и пабов для Microsoft S'L Server.](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

В этой статье показано, как создать службу данных с помощью поставщика Entity Framework. Доступны другие поставщики служб данных. Для получения дополнительной [информации см.](data-services-providers-wcf-data-services.md)

После создания службы требуется явно предоставить доступ к ресурсам службы данных. Для получения дополнительной информации [см.](how-to-enable-access-to-the-data-service-wcf-data-services.md)

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Создание веб-приложения ASP.NET, которое работает на IIS

1. В Visual Studio в меню **Файл** выберите пункты **Создать** > **Проект**.

2. В диалоговом окне **нового проекта** выберите **«Установленную** >»**(Visual C)** или **«Visual Basic»**> **веб-категории.**

3. Выберите шаблон **Веб-приложение ASP.NET** .

4. Введите `NorthwindService` как название проекта.

5. Нажмите кнопку **ОК**.

6. В меню **проекта** выберите **недвижимость NorthwindService.**

7. Выберите **web-вкладку,** а затем выберите **Используйте локальный веб-сервер IIS.**

8. Нажмите **Создать виртуальный каталог,** а затем нажмите **OK**.

9. С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).

    - 32-разрядные системы:

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - 64-разрядные системы:

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     Она регистрирует Windows Communication Foundation (WCF) на компьютере.

10. С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).

    - 32-разрядные системы:

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - 64-разрядные системы:

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     Это необходимо для того, чтобы проверить правильность работы служб IIS после установки WCF на компьютере. Возможно, потребуется перезапустить службы IIS.

11. Если приложение ASP.NET запущено в службах IIS7, нужно также выполнить следующие действия.

    1. Откройте IIS Manager и перейдите к приложению PhotoService под **веб-узлом по умолчанию.**

    2. В окне **Просмотр возможностей** дважды щелкните элемент **Проверка подлинности**.

    3. На странице **Проверка подлинности** выберите **Анонимная проверка подлинности**.

    4. В панели **действий** щелкните **Edit,** чтобы установить принцип безопасности, под которым анонимные пользователи будут подключаться к сайту.

    5. В диалоговом окне **учетных данных Edit Anonymous Authentication credentials** выберите **идентичуение пула приложений.**

    > [!IMPORTANT]
    > При использовании учетной записи сетевой службы анонимным пользователям предоставляется доступ к внутренней сети, связанной с этой учетной записью.

12. С помощью среды SQL Server Management Studio, программы sqlcmd.exe или редактора Transact-SQL в Visual Studio выполните следующую команду Transact-SQL для экземпляра SQL Server с прикрепленной базой данных Northwind.

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    Она создает имя входа в экземпляр SQL Server для учетной записи Windows, используемой для запуска служб IIS. Это позволит службам IIS подключиться к экземпляру SQL Server.

13. После присоединения базы данных Northwind выполните следующие команды Transact-SQL:

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

    Они предоставляют право на новое имя входа, позволяющее службам IIS читать данные из базы данных Northwind и записывать данные в эту базу данных.

## <a name="define-the-data-model"></a>Определение модели данных

1. В **Solution Explorer**, правой кнопкой мыши имя ASP.NET проекта, а затем нажмите **Добавить** > **новый пункт**.

2. В диалоговом окне **Добавить новый элемент** выберите **ADO.NET модель данных entity.**

3. Для названия модели данных `Northwind.edmx`введите тип .

4. В Волшебник модели данных Сущности выберите **Generate из базы данных,** а затем нажмите **далее**.

5. Подключите модель данных к базе данных, выдвив один из следующих шагов, а затем нажмите **Далее:**

    - Если у вас нет уже настроенного соединения базы данных, нажмите **New Connection** и создайте новое соединение. Дополнительные сведения см. в разделе [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.

         \- или -

    - Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.

6. На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.

7. Чтобы завершить работу мастера, нажмите кнопку **Готово** .

## <a name="create-the-data-service"></a>Создание службы данных

1. В **Solution Explorer**, правой кнопкой мыши имя вашего ASP.NET проекта, а затем нажмите **Добавить** > **новый пункт**.

2. В диалоговом окне **Добавить новый элемент** выберите **службу данных WCF.**

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Шаблон **WCF Data Service** доступен в Visual Studio 2015, но не в Visual Studio 2017 или позже.

3. Для названия службы, `Northwind`введите .

     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода. В **Solution Explorer**служба имеет название, Northwind и расширение .svc.cs или .svc.vb.

4. В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`. Определение класса должно выглядеть следующим образом.

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>См. также

- [Предоставление данных как службы](exposing-your-data-as-a-service-wcf-data-services.md)
