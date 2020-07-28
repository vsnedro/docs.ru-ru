---
title: Пошаговое руководство. Отображение данных из базы данных SQL Server в элементе управления DataGrid
description: Узнайте, как получать данные из базы данных SQL Server и отображать их в элементе управления Windows Presentation Foundation DataGrid с помощью этого пошагового руководства.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: cc41979c869021c9c363f3f68ce590d4702e068c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167556"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Пошаговое руководство. Отображение данных из SQL Server базы данных в элементе управления DataGrid

В этом пошаговом руководстве вы получаете данные из базы данных SQL Server и отображает их в <xref:System.Windows.Controls.DataGrid> элементе управления. Entity Framework ADO.NET используется для создания классов сущностей, представляющих данные, и использования LINQ для написания запроса, который извлекает указанные данные из класса сущностей.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого пошагового руководства требуются следующие компоненты:

- Visual Studio.

- Доступ к выполняющемуся экземпляру SQL Server или SQL Server Express, к которому присоединен образец базы данных AdventureWorks. Базу данных AdventureWorks можно загрузить с сайта [GitHub](https://github.com/Microsoft/sql-server-samples/releases).

## <a name="create-entity-classes"></a>Создание классов сущностей

1. Создайте новый проект приложения WPF в Visual Basic или C# и присвойте ему имя `DataGridSQLExample` .

2. В обозреватель решений щелкните правой кнопкой мыши проект, наведите указатель на пункт **Добавить**и выберите пункт **создать элемент**.

     Откроется диалоговое окно Добавить новый элемент.

3. В области Установленные шаблоны выберите **данные** и в списке шаблонов выберите **ADO.NET EDM**.

     ![Шаблон элемента EDM ADO.NET](../../wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4. Присвойте файлу имя `AdventureWorksModel.edmx` и нажмите кнопку **Добавить**.

     Появится мастер модели EDM.

5. На экране Выбор содержимого модели выберите **конструктор EF из базы данных** , а затем нажмите кнопку **Далее**.

6. На экране Выбор подключения к данным укажите подключение к базе данных AdventureWorksLT2008. Дополнительные сведения см. в разделе [диалоговое окно "Выбор подключения к данным"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).

    Убедитесь, что имя имеет значение, `AdventureWorksLT2008Entities` а флажок **сохранить параметры подключения сущности в App.Config как** установлен, а затем нажмите кнопку **Далее**.

7. На экране Выбор объектов базы данных разверните узел таблицы и выберите таблицы **Product** и **ProductCategory** .

     Можно создавать классы сущностей для всех таблиц. Однако в этом примере данные извлекаются только из этих двух таблиц.

     ![Выбор пунктов Product и ProductCategory из таблиц](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")

8. Нажмите кнопку **Готово**.

     Сущности Product и ProductCategory отображаются в Entity Designer.

     ![Модели сущностей Product и ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")

## <a name="retrieve-and-present-the-data"></a>Получение и представление данных

1. Откройте файл MainWindow. XAML.

2. Установите свойство в значение <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Window> 450.

3. В редакторе XAML добавьте следующий <xref:System.Windows.Controls.DataGrid> тег между `<Grid>` тегами и, `</Grid>` чтобы добавить <xref:System.Windows.Controls.DataGrid> именованный объект `dataGrid1` .

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     ![Окно с DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")

4. Выберите <xref:System.Windows.Window>.

5. С помощью окно свойств или редактора XAML Создайте обработчик событий для <xref:System.Windows.Window> именованного `Window_Loaded` <xref:System.Windows.FrameworkElement.Loaded> события. Дополнительные сведения см. [в разделе инструкции. Создание простого обработчика событий](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

     Ниже показан XAML для MainWindow. XAML.

    > [!NOTE]
    > При использовании Visual Basic в первой строке файла MainWindow. XAML замените на `x:Class="DataGridSQLExample.MainWindow"` `x:Class="MainWindow"` .

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. Откройте файл кода программной части (MainWindow. XAML. vb или MainWindow.xaml.cs) для <xref:System.Windows.Window> .

7. Добавьте следующий код, чтобы получить только определенные значения из соединяемых таблиц и задать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для свойства объекта <xref:System.Windows.Controls.DataGrid> результаты запроса.

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. Запустите пример.

     Вы увидите <xref:System.Windows.Controls.DataGrid> , что отображает данные.

     ![DataGrid с данными из базы данных SQL](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")

## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.DataGrid>
