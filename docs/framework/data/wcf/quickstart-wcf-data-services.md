---
description: 'Дополнительные сведения: Краткое руководство (службы данных WCF)'
title: Краткое руководство (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 92a1b8882f6a7db2ed33f032ad434efd06400421
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794953"
---
# <a name="quickstart-wcf-data-services"></a>Краткое руководство (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Это краткое руководство поможет вам ознакомиться с службы данных WCF и Open Data Protocol (OData) с помощью серии задач, которые поддерживают разделы в [Начало работы](getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Что вы узнаете

В первой задаче этого краткого руководства показано, как создать службу данных для предоставления веб-канала OData из образца базы данных Northwind. В последующих разделах вы получите доступ к каналу OData с помощью веб-браузера, а также создаете клиентское приложение Windows Presentation Foundation (WPF), которое использует канал OData с помощью клиентских библиотек.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого краткого руководства установите следующие компоненты:

- Visual Studio

- Экземпляр SQL Server. К ним относятся SQL Server Express, включенные в установку Visual Studio 2015 по умолчанию или как часть рабочей нагрузки **хранения и обработки данных** в visual Studio 2017 или более поздней версии.

- Наличие учебной базы данных Northwind. Чтобы установить базу данных, выполните скрипт Transact-SQL из [баз данных Northwind и Pubs для Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).

## <a name="wcf-data-services-quickstart-tasks"></a>Краткие задачи служб данных WCF

 [Создание службы данных](creating-the-data-service.md)

 Определите приложение ASP.NET, определите модель данных, создайте службу данных и включите доступ к ресурсам.

 [Доступ к службе из веб-браузера](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Запустите службу из среды Visual Studio и обратитесь к ней с помощью запросов HTTP GET через веб-браузер для получения доступа к предоставляемым каналам.

 [Создание клиентского приложения платформа .NET Framework](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Создание приложения WPF для использования веб-канала OData, привязки данных к элементам управления Windows, изменения данных в связанных элементах управления и последующей отправки изменений обратно в службу данных.

> [!NOTE]
> Файлы проекта из готовой версии краткого руководства можно скачать с сайта [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Запуск краткого руководства](creating-the-data-service.md)

## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../adonet/ef/index.md)
