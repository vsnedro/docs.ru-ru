---
description: Дополнительные сведения см. в статье как вернуть результат запроса LINQ в виде определенного типа (Visual Basic)
title: Практическое руководство. Возвращение результата запроса LINQ в виде определенного типа
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 8abeb3b5f174b1671415cbb55f35952e3bc77e7d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425663"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a>Практическое руководство. Возвращение результата запроса LINQ в виде определенного типа (Visual Basic)

Language-Integrated query (LINQ) упрощает доступ к сведениям о базе данных и выполнение запросов. По умолчанию запросы LINQ возвращают список объектов в виде анонимного типа. Можно также указать, что запрос возвращает список определенного типа с помощью `Select` предложения.  
  
 В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и проецирует результаты в виде определенного именованного типа. Дополнительные сведения см. в разделе [анонимные типы](../objects-and-classes/anonymous-types.md) и [предложение SELECT](../../../language-reference/queries/select-clause.md).  
  
 В примерах этого раздела используется учебная база данных Northwind. Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Создание соединения с базой данных  
  
1. В Visual Studio откройте **Обозреватель сервера** / **Обозреватель базы данных** , выбрав в  / меню **вид** пункт Обозреватель сервера **Обозреватель базы данных** .  
  
2. Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера** / **Обозреватель базы данных** а затем выберите команду **Добавить подключение**.  
  
3. Укажите допустимое соединение с образцом базы данных Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Добавление проекта, содержащего файл LINQ to SQL  
  
1. В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.  
  
2. В меню **Проект** выберите **Добавить новый элемент**. Выберите шаблон элемента **LINQ to SQL классы** .  
  
3. Задайте файлу имя `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблиц в запрос в реляционный конструктор O/R  
  
1. В **Обозреватель сервера** / **Обозреватель базы данных** разверните подключение к базе данных Northwind. Разверните папку **Таблицы**.  
  
     Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.  
  
2. Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.  
  
     Конструктор создает новый `Customer` объект для проекта. Результат запроса можно проецировать в виде `Customer` типа или в виде создаваемого типа. Этот пример создаст новый тип в следующей процедуре и запишет результат запроса в качестве этого типа.  
  
3. Сохраните изменения и закройте конструктор.  
  
4. Сохраните проект.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса к базе данных и вывода результатов  
  
1. Перетащите элемент управления из **области элементов** в <xref:System.Windows.Forms.DataGridView> форму Windows по умолчанию для проекта, Form1.  
  
2. Дважды щелкните Form1, чтобы изменить класс Form1.  
  
3. После `End Class` оператора класса Form1 добавьте следующий код, чтобы создать `CustomerInfo` тип для хранения результатов запроса для этого примера.  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. При добавлении таблиц в реляционный конструктор объектов конструктор добавил в <xref:System.Data.Linq.DataContext> проект объект. Этот объект содержит код, который необходим для доступа к этим таблицам и для доступа к отдельным объектам и коллекциям для каждой таблицы. Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла. Для этого проекта объект называется <xref:System.Data.Linq.DataContext> `northwindDataContext` .  
  
     В коде можно создать экземпляр класса <xref:System.Data.Linq.DataContext> и запросить таблицы, заданные конструктором O/R.  
  
     В `Load` событии класса Form1 добавьте следующий код для запроса таблиц, предоставляемых как свойства контекста данных. `Select`Предложение запроса создаст новый `CustomerInfo` тип, а не анонимный тип для каждого элемента результата запроса.  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также раздел

- [LINQ](index.md)
- [Запросы](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
