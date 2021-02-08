---
description: 'Дополнительные сведения о: SqlDependency в приложении ASP.NET'
title: SqlDependency в приложении ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 686586af834884f97ff8e62fdc792b3cdc23f507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767028"
---
# <a name="sqldependency-in-an-aspnet-application"></a>SqlDependency в приложении ASP.NET

В приведенном в этом разделе примере показано, как применять <xref:System.Data.SqlClient.SqlDependency> косвенно, используя объект <xref:System.Web.Caching.SqlCacheDependency> ASP.NET. Объект <xref:System.Web.Caching.SqlCacheDependency> использует <xref:System.Data.SqlClient.SqlDependency> для прослушивания уведомлений и корректного обновления кэша.  
  
> [!NOTE]
> В примере кода предполагается, что вы включили уведомления о запросах, выполняя скрипты, [включив уведомления о запросах](enabling-query-notifications.md).  
  
## <a name="about-the-sample-application"></a>О примере приложения  

 В примере приложения используется одна веб-страница ASP.NET для вывода сведений о продуктах из базы данных **AdventureWorks** SQL Server в элемент управления <xref:System.Web.UI.WebControls.GridView>. При загрузке страницы код записывает текущее время в элемент управления <xref:System.Web.UI.WebControls.Label>. Затем он определяет объект <xref:System.Web.Caching.SqlCacheDependency> и задает свойства объекта <xref:System.Web.Caching.Cache> для сохранения данных кэша до трех минут. Затем код подключается к базе данных и получает данные. При загрузке страницы и работе приложения ASP.NET будет получать данные из кэша, которые можно проверить, отметив, что время на странице не меняется. Если наблюдаемые данные изменяются, ASP.NET делает недействительным кэш и повторно заполняет элемент управления `GridView` новыми данными, обновляя время в элементе управления `Label`.  
  
## <a name="creating-the-sample-application"></a>Создание примера приложения  

 Чтобы создать и запустить пример приложения, выполните следующие действия:  
  
1. Создание нового веб-сайта ASP.NET.  
  
2. Добавьте <xref:System.Web.UI.WebControls.Label> и элемент управления <xref:System.Web.UI.WebControls.GridView> на страницу Default.aspx.  
  
3. Откройте модуль класса страницы и добавьте следующие директивы:  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. Добавьте следующий код в событие `Page_Load` страницы:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. Добавьте два вспомогательных метода: `GetConnectionString` и `GetSQL`. В определенной строке соединения используются интегрированные средства безопасности. Необходимо будет убедиться, что используемая учетная запись обладает необходимыми разрешениями для базы данных, а в образце базы данных **AdventureWorks** включены уведомления.
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Тестирование приложения  

 Приложение кэширует данные, отображаемые в веб-форме, и обновляет их каждые три минуты, если нет действий. Если в базе данных происходит изменение, кэш обновляется немедленно. Запустите приложение из Visual Studio, чтобы загрузить страницу в браузер. Отображаемое время обновления кэша указывает, когда кэш был обновлен последний раз. Подождите три минуты, а затем обновите страницу, в результате чего произойдет событие обратной передачи. Обратите внимание, что время, отображаемое на странице, изменилось. Если обновить страницу меньше чем через три минуты, время, отображаемое на странице, останется прежним.  
  
 Теперь обновите данные в базе данных, используя команду Transact-SQL UPDATE, и обновите страницу. Отображаемое время теперь указывает, что кэш был обновлен с учетом новых данных из базы данных. Обратите внимание, что хотя кэш обновляется, время на странице не изменяется, пока не произойдет событие обратной передачи.  

## <a name="distributed-cache-synchronization-using-sql-dependency"></a>Синхронизация распределенного кэша с использованием зависимости SQL

Некоторые из таких распределенных кэшей, как [NCache](https://www.alachisoft.com/ncache) , обеспечивают поддержку синхронизации базы данных SQL и кэша с помощью [зависимости SQL](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html). Дополнительные сведения и пример реализации исходного кода см. в разделе [Пример использования зависимости SQL для распределенного кэша](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).

## <a name="see-also"></a>См. также

- [Уведомления о запросах в SQL Server](query-notifications-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
