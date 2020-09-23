---
title: Практическое руководство. Выполнение запросов к базе данных с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: 60dbe3b4e164e266202cac4abaea009869d08cc4
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075269"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a>Практическое руководство. Выполнение запросов к базе данных с помощью LINQ (Visual Basic)

LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.  
  
 В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server.  
  
 В примерах этого раздела используется учебная база данных Northwind. Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a>Создание соединения с базой данных  
  
1. В Visual Studio откройте **Обозреватель сервера** / **Обозреватель базы данных** , выбрав в **Server Explorer** / меню **вид** пункт Обозреватель сервера**Обозреватель базы данных** .  
  
2. Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера** / **Обозреватель базы данных** а затем выберите команду **Добавить подключение**.  
  
3. Укажите допустимое соединение с образцом базы данных Northwind.  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Добавление проекта, содержащего файл LINQ to SQL  
  
1. В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.  
  
2. В меню **Проект** выберите **Добавить новый элемент**. Выберите шаблон элемента **LINQ to SQL классы** .  
  
3. Задайте файлу имя `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблиц в запрос в реляционный конструктор O/R  
  
1. В **Обозреватель сервера** / **Обозреватель базы данных**разверните подключение к базе данных Northwind. Разверните папку **Таблицы**.  
  
     Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.  
  
2. Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора. Щелкните таблицу Orders и перетащите ее на левую панель конструктора.  
  
     Конструктор создает `Customer` `Order` для проекта новые объекты и. Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов. Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойство для всех заказов, связанных с этим клиентом.  
  
3. Сохраните изменения и закройте конструктор.  
  
4. Сохраните проект.  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса к базе данных и вывода результатов  
  
1. Перетащите элемент управления из **области элементов**в <xref:System.Windows.Forms.DataGridView> форму Windows по умолчанию для проекта, Form1.  
  
2. Дважды щелкните Form1, чтобы добавить код в `Load` событие в форме.  
  
3. При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объект для проекта. Этот объект содержит код, который необходим для доступа к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы. Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла. Для этого проекта объект называется <xref:System.Data.Linq.DataContext> `northwindDataContext` .  
  
     В коде можно создать экземпляр класса <xref:System.Data.Linq.DataContext> и запросить таблицы, заданные конструктором O/R.  
  
     Добавьте следующий код в `Load` событие для запроса таблиц, предоставляемых в качестве свойств контекста данных.  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
5. Ниже приведены некоторые дополнительные запросы, которые можно использовать.  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a>См. также

- [LINQ](index.md)
- [Запросы](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
