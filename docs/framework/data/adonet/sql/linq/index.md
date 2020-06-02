---
title: LINQ to SQL
description: LINQ to SQL является компонентом .NET Framework, который предоставляет инфраструктуру времени выполнения для управления реляционными данными как объектами.
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 13502bfee3ee24764d190dace1512bc958343973
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286317"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]является компонентом .NET Framework версии 3,5, предоставляющей инфраструктуру времени выполнения для управления реляционными данными как объектами.  
  
> [!NOTE]
> Реляционные данные отображаются в виде коллекции двумерных таблиц (*отношений* или *плоских файлов*),где общие столбцы связывают таблицы друг с другом. Для эффективного использования [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] необходимо ознакомиться с основными принципами реляционных баз данных.  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] модель данных реляционной базы данных сопоставляется объектной модели, выраженной в языке программирования разработчика. При запуске приложения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запросы LINQ из объектной модели в SQL и отправляет их в базу данных для выполнения. Когда база данных возвращает результаты, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует их обратно в объекты, с которыми можно работать на собственном языке программирования.  
  
 Разработчики, использующие Visual Studio, обычно используют реляционный конструктор объектов, который предоставляет пользовательский интерфейс для реализации многих функций [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
 Документация, включенная в эту версию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], описывает основные строительные блоки, процессы и методики, необходимые для построения приложений [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Можно также выполнить поиск по Документация Майкрософт для конкретных проблем, и вы можете принять участие в [форуме LINQ](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), где вы сможете обсуждать более сложные темы подробно с экспертами. Наконец, [LINQ to SQL: запрос на языке .NET для реляционных данных](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) , содержащий технические сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] технологии, завершен с помощью Visual Basic и примеров кода C#.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Начало работы](getting-started.md)  
 Содержит краткие общие сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], а также сведения о начале работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Руководство по программированию](programming-guide.md)  
 Содержит описание действий по сопоставлению, осуществлению запросов, обновлению, отладке и выполнению схожих задач.  
  
 [Ссылки](reference.md)  
 Содержит справочные сведения о ряде аспектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Представлены следующие разделы: "Сопоставление типов SQL-CLR", "Преобразование стандартного оператора запросов" и многие другие.  
  
 [Примеры](samples.md)  
 Содержит ссылки на примеры Visual Basic и C#.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Интегрированный в язык запрос (LINQ) — C #](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 Предоставляет обзоры технологий LINQ в C#.

 [LINQ — Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Предоставляет обзоры технологий LINQ в Visual Basic.
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Описывает технологии LINQ для Visual Basic пользователей.  
  
 [LINQ и ADO.NET](../../linq-and-ado-net.md)  
 Ссылки на портал ADO.NET.  
  
 [Пошаговые руководства LINQ to SQL](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 Содержит список пошаговых руководств, доступных для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Загрузка примеров баз данных](downloading-sample-databases.md)  
 Содержит инструкции по загрузке примеров баз данных, используемых в документации.  
  
 [Обзор серверного веб-элемента управления LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))  
 Описывает, как <xref:System.Web.UI.WebControls.LinqDataSource> элемент управления предоставляет веб-разработчикам запрос к языку (LINQ) через архитектуру управления источниками данных ASP.NET.
