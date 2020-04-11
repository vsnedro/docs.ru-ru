---
title: Краткое руководство (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121215"
---
# <a name="quickstart-wcf-data-services"></a>Краткое руководство (службы данных WCF)

Этот быстрый запуск поможет вам ознакомиться с WCF Data Services и Протоколом открытых данных (OData) с помощью ряда задач, которые поддерживают темы в [Getting Started](getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Что вы узнаете

Первая задача в этом быстром запуске показывает, как создать службу данных для разоблачения ленты OData из базы данных Northwind. В более поздних темах вы получите доступ к ленте OData с помощью веб-браузера, а также создадите клиентское приложение Windows Presentation Foundation (WPF), которое потребляет канал OData с помощью клиентских библиотек.

## <a name="prerequisites"></a>Предварительные требования

Чтобы завершить этот быстрый запуск, установите следующие компоненты:

- Visual Studio

- Экземпляр сервера S'L. Это включает в себя S'L Server Express, который включен в установку Visual Studio 2015 по умолчанию, или как часть рабочей нагрузки **хранения и обработки данных** в Visual Studio 2017 или позже.

- Наличие учебной базы данных Northwind. Для установки базы данных запустите скрипт Transact-S'L из [баз данных Northwind и пабов для Microsoft S'L Server.](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

## <a name="wcf-data-services-quickstart-tasks"></a>Службы быстрого запуска данных WCF

 [Создание службы данных](creating-the-data-service.md)

 Определите приложение ASP.NET, определите модель данных, создайте службу данных и включите доступ к ресурсам.

 [Доступ к Службе из веб-браузера](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Запустите службу из среды Visual Studio и обратитесь к ней с помощью запросов HTTP GET через веб-браузер для получения доступа к предоставляемым каналам.

 [Создание приложения для клиентов-клиентов.NET Framework](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Создайте приложение WPF для использования ленты OData, привяжните данные к элементам управления Windows, измените данные в связанных элементах управления, а затем отправьте изменения обратно в службу данных.

> [!NOTE]
> Файлы проекта из завершенной версии quickstart можно загрузить с [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Начать быстрый запуск](creating-the-data-service.md)

## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../adonet/ef/index.md)
