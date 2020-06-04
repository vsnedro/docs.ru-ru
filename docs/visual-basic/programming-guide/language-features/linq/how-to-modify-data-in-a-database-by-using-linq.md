---
title: Практическое руководство. Изменение данных в базе данных с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: eb076d9156fa66858f2e560422eef0dc61ba22b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403489"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)

Запросы LINQ позволяют легко получить доступ к сведениям о базе данных и изменить значения в базе данных.

В следующем примере показано, как создать новое приложение, которое извлекает и обновляет сведения в базе данных SQL Server.

В примерах этого раздела используется учебная база данных Northwind. Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).

### <a name="to-create-a-connection-to-a-database"></a>Создание соединения с базой данных

1. В Visual Studio откройте **Обозреватель сервера** / **Обозреватель базы данных** , выбрав в меню **вид** пункт **Обозреватель сервера** / **Обозреватель базы данных**.

2. Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера** / **Обозреватель базы данных**и выберите команду **Добавить подключение**.

3. Укажите допустимое соединение с образцом базы данных Northwind.

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Добавление проекта с файлом LINQ to SQL

1. В Visual Studio в меню **файл** наведите указатель мыши на пункт **создать** и выберите **проект**. Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.

2. В меню **Проект** выберите **Добавить новый элемент**. Выберите шаблон элемента **LINQ to SQL классы** .

3. Задайте файлу имя `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла открывается реляционный конструктор объектов (реляционный конструктор R) `northwind.dbml` .

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Добавление таблиц к запросам и их изменение в конструкторе

1. В **Обозреватель сервера** / **Обозреватель базы данных**разверните подключение к базе данных Northwind. Разверните папку **Таблицы**.

     Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув `northwind.dbml` файл, добавленный ранее.

2. Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.

     Конструктор создает новый объект Customer для вашего проекта.

3. Сохраните изменения и закройте конструктор.

4. Сохраните проект.

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Добавление кода для изменения базы данных и вывода результатов

1. Перетащите элемент управления из **области элементов**в <xref:System.Windows.Forms.DataGridView> форму Windows по умолчанию для проекта, Form1.

2. При добавлении таблиц в реляционный конструктор объектов конструктор добавил в <xref:System.Data.Linq.DataContext> проект объект. Этот объект содержит код, который можно использовать для доступа к таблице Customers. Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы. Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла. Для этого проекта объект называется <xref:System.Data.Linq.DataContext> `northwindDataContext` .

     Можно создать экземпляр <xref:System.Data.Linq.DataContext> объекта в коде и запросить и изменить коллекцию Customers, указанную в конструкторе O/R. Изменения, вносимые в коллекцию Customers, не отражаются в базе данных до их отправки путем вызова <xref:System.Data.Linq.DataContext.SubmitChanges%2A> метода <xref:System.Data.Linq.DataContext> объекта.

     Дважды щелкните форму Windows Forms, форму Form1, чтобы добавить код в <xref:System.Windows.Forms.Form.Load> событие, чтобы запросить таблицу Customers, доступную в качестве свойства <xref:System.Data.Linq.DataContext> . Добавьте следующий код:

    ```vb
    Private db As northwindDataContext

    Private Sub Form1_Load(ByVal sender As System.Object,
                           ByVal e As System.EventArgs
                          ) Handles MyBase.Load
      db = New northwindDataContext()

      RefreshData()
    End Sub

    Private Sub RefreshData()
      Dim customers = From cust In db.Customers
                      Where cust.City(0) = "W"
                      Select cust

      DataGridView1.DataSource = customers
    End Sub
    ```

3. Перетащите на форму три элемента управления из **панели элементов** <xref:System.Windows.Forms.Button> . Выберите первый `Button` элемент управления. В окне **Свойства** присвойте свойству `Name` `Button` элемента управления значение `AddButton` и значение `Text` `Add` . Нажмите вторую кнопку и задайте `Name` свойству значение `UpdateButton` , а `Text` свойству — значение `Update` . Нажмите третью кнопку и задайте `Name` свойству значение `DeleteButton` , а `Text` свойству — значение `Delete` .

4. Дважды щелкните кнопку **Добавить** , чтобы добавить код к `Click` событию. Добавьте следующий код:

    ```vb
    Private Sub AddButton_Click(ByVal sender As System.Object,
                                ByVal e As System.EventArgs
                               ) Handles AddButton.Click
      Dim cust As New Customer With {
        .City = "Wellington",
        .CompanyName = "Blue Yonder Airlines",
        .ContactName = "Jill Frank",
        .Country = "New Zealand",
        .CustomerID = "JILLF"}

      db.Customers.InsertOnSubmit(cust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

5. Дважды щелкните кнопку " **Обновить** ", чтобы добавить код в `Click` событие. Добавьте следующий код:

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. Дважды щелкните кнопку **Удалить** , чтобы добавить код в `Click` событие. Добавьте следующий код:

    ```vb
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles DeleteButton.Click
      Dim deleteCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      db.Customers.DeleteOnSubmit(deleteCust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

7. Нажмите клавишу F5 для запуска проекта. Нажмите кнопку **Добавить** , чтобы добавить новую запись. Нажмите кнопку **Обновить** , чтобы изменить новую запись. Нажмите кнопку **Удалить** , чтобы удалить новую запись.

## <a name="see-also"></a>См. также раздел

- [LINQ](index.md)
- [Запросы](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор R)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
