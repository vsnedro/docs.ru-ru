---
title: Создание службы данных WCF в Visual Studio
description: Узнайте, как создать образец службы данных, который использует WCF Data Services для предоставления веб-канала OData на основе образца базы данных.
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 739cb6971209792724a2e939ca4f4821d5879c8c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247795"
---
# <a name="create-the-data-service"></a>Создание службы данных

В этом разделе вы создадите образец службы данных, который использует WCF Data Services для предоставления веб-канала Open Data Protocol (OData), основанного на образце базы данных Northwind. Задача включает следующие основные шаги.

1. создайте веб-приложение ASP.NET;

2. Определение модели данных с использованием средств для работы с моделью EDM.

3. Добавление службы данных в веб-приложение.

4. Включите доступ к службе данных.

## <a name="create-the-aspnet-web-app"></a>Создание веб-приложения ASP.NET

1. В Visual Studio в меню **Файл** выберите пункты **Создать** > **Проект**.

1. В диалоговом окне **Новый проект** в разделе Visual Basic или Visual C# выберите категорию **веб-узел** , а затем выберите **ASP.NET Web Application (веб-приложение**).

1. Введите в `NorthwindService` качестве имени проекта и нажмите кнопку **ОК**.

1. В диалоговом окне **новое веб-приложение ASP.NET** выберите **пусто** и нажмите кнопку **ОК**.

1. (Необязательно) Укажите конкретный номер порта для веб-приложения. Примечание. номер порта `12345` используется в этой серии кратких руководств.

    1. В **Обозреватель решений**щелкните правой кнопкой мыши только что созданный проект ASP.NET, а затем выберите пункт **свойства**.

    2. Перейдите на вкладку **веб** и задайте для параметра **конкретный порт** значение `12345` .

## <a name="define-the-data-model"></a>Определение модели данных

1. В **Обозреватель решений**щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавить**  >  **новый элемент**.

2. В диалоговом окне **Добавление нового элемента** выберите категорию **данные** , а затем выберите **ADO.NET EDM**.

3. В качестве имени модели данных введите `Northwind.edmx` .

4. В **мастере EDM**выберите элемент **конструктор EF из базы данных**, а затем нажмите кнопку **Далее**.

5. Подключите модель данных к базе данных, выполнив одно из следующих действий, а затем нажмите кнопку **Далее**.

    - Если подключение к базе данных уже не настроено, щелкните **создать подключение** и создайте новое подключение. Дополнительные сведения см. в разделе [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.

         \- или -

    - Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.

6. На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.

7. Чтобы завершить работу мастера, нажмите кнопку **Готово** .

## <a name="create-the-wcf-data-service"></a>Создание службы данных WCF

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект ASP.NET и выберите команду **Добавить**  >  **новый элемент**.

2. В диалоговом окне **Добавление нового элемента** выберите шаблон элемента **службы данных WCF** из категории **веб** .

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Шаблон **службы данных WCF** доступен в visual Studio 2015, но не в visual Studio 2017 или более поздней версии.

3. В качестве имени службы введите `Northwind` .

     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода. В **Обозреватель решений**служба имеет имя Northwind с расширением *SVC.CS* или *SVC. vb*.

4. В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`. Определение класса должно выглядеть следующим образом.

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>Разрешение доступа к ресурсам службы данных

1. В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     Это обеспечивает авторизованным клиентам доступ для чтения и записи к ресурсам указанных наборов сущностей.

    > [!NOTE]
    > Любой клиент, имеющий доступ к приложению ASP.NET, имеет также доступ к ресурсам, предоставляемым службой данных. Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения. Дополнительные сведения см. в разделе [Securing WCF Data Services](securing-wcf-data-services.md).

## <a name="next-steps"></a>Дальнейшие действия

Вы успешно создали новую службу данных, которая предоставляет канал OData, основанный на образце базы данных Northwind, и вы включили доступ к каналу для клиентов, имеющих разрешения для веб-приложения ASP.NET. Далее вы запустите службу данных из Visual Studio и получите доступ к каналу OData, отправив запросы HTTP GET через веб-браузер:

> [!div class="nextstepaction"]
> [Доступ к службе из веб-браузера](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>См. также

- [Средства EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
