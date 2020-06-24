---
title: Библиотека клиентов служб данных WCF
description: Узнайте, как использовать клиентские библиотеки WCF Data Services для доступа к данным и их изменения из клиентского приложения .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 58d038d5c2ac4973c2b41f4d49c1746f48f2a2fb
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247744"
---
# <a name="wcf-data-services-client-library"></a>Библиотека клиентов служб данных WCF
Любое приложение может взаимодействовать со службой данных на основе Open Data Protocol (OData), если она может отправить HTTP-запрос и обработать канал OData, возвращаемый службой данных. Такое взаимодействие позволяет получать доступ к службам на основе OData из широкого спектра веб-приложений. WCF Data Services включает клиентские библиотеки, обеспечивающие более широкие возможности программирования при использовании веб-каналов OData из .NET Framework или приложений на основе Silverlight.  
  
 Клиентская библиотека содержит два основных класса: <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601>. Класс <xref:System.Data.Services.Client.DataServiceContext> инкапсулирует операции, поддерживающие работу с конкретной службой данных. Несмотря на то, что службы OData не имеют состояния, контекст не имеет. Таким образом, класс можно использовать <xref:System.Data.Services.Client.DataServiceContext> для поддержания состояния на стороне клиента между взаимодействием со службой данных для поддержки таких функций, как управление изменениями. Этот класс также управляет идентификаторами и отслеживает изменения. Класс <xref:System.Data.Services.Client.DataServiceQuery%601> представляет запрос к определенному набору сущностей.  
  
 Этот раздел описывает использование клиентских библиотек для доступа и изменения данных из клиентского приложения .NET Framework. Дополнительные сведения об использовании клиентской библиотеки WCF Data Services с приложением на основе Silverlight см. в разделе [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v%3dvs.95)). Доступны другие клиентские библиотеки, позволяющие использовать канал OData в приложениях других типов. Дополнительные сведения о пакете OData SDK см. в разделе [пример кода для ODATA SDK](https://www.odata.org/ecosystem/#sdk).
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание библиотеки клиентов службы данных](generating-the-data-service-client-library-wcf-data-services.md)  
 Описывает, как создать клиентскую библиотеку и клиентские классы службы данных, основанные на каналах OData.  
  
 [Выполнение запросов к службе данных](querying-the-data-service-wcf-data-services.md)  
 Описывает выполнение запросов к службе данных из приложения на основе .NET Framework с помощью клиентских библиотек.  
  
 [Загрузка отложенного содержимого](loading-deferred-content-wcf-data-services.md)  
 Описывает загрузку дополнительного содержимого, не включенного в первоначальный ответ на запрос.  
  
 [Обновление службы данных](updating-the-data-service-wcf-data-services.md)  
 Описывает создание, изменение и удаление сущностей и отношений с помощью клиентских библиотек.  
  
 [Асинхронные операции](asynchronous-operations-wcf-data-services.md)  
 Описывает возможности, предоставляемые клиентскими библиотеками для асинхронной работы со службой данных.  
  
 [Пакетные операции](batching-operations-wcf-data-services.md)  
 Описывает отправку нескольких запросов к службе данных в одном пакете с помощью клиентских библиотек.  
  
 [Привязка данных к элементам управления](binding-data-to-controls-wcf-data-services.md)  
 Описывает, как привязать элементы управления к каналу OData, возвращенному службой данных.  
  
 [Вызов операций служб](calling-service-operations-wcf-data-services.md)  
 Описывает, как использовать клиентскую библиотеку для вызова операций службы.  
  
 [Управление контекстом службы данных](managing-the-data-service-context-wcf-data-services.md)  
 Описывает параметры управления режимом работы клиентской библиотеки.  
  
 [Работа с двоичными данными](working-with-binary-data-wcf-data-services.md)  
 Описывает доступ к двоичным данным, возвращенным службой данных в виде потока данных, и их изменение.  
  
## <a name="see-also"></a>См. также

- [Определение служб данных WCF](defining-wcf-data-services.md)
- [Начало работы](getting-started-with-wcf-data-services.md)
