---
title: Практическое руководство. Вызов хранимой процедуры с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: b451642a16f36c4f7fd19c853fdfd2282f5bede5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405034"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)
LINQ позволяет легко получить доступ к информации базы данных, включая объекты базы данных, такие как хранимые процедуры.  
  
 В следующем примере показано, как создать приложение, вызывающее хранимую процедуру в SQL Server базе данных. В этом примере показано, как вызвать две различные хранимые процедуры в базе данных. Каждая процедура возвращает результаты запроса. Одна процедура принимает входные параметры, а другая процедура не принимает параметры.  
  
 В примерах этого раздела используется учебная база данных Northwind. Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Создание соединения с базой данных  
  
1. В Visual Studio откройте **Обозреватель сервера** / **Обозреватель базы данных** , выбрав в **Server Explorer** / меню **вид** пункт Обозреватель сервера**Обозреватель базы данных** .  
  
2. Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера** / **Обозреватель базы данных** а затем выберите команду **Добавить подключение**.  
  
3. Укажите допустимое соединение с образцом базы данных Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Добавление проекта, содержащего файл LINQ to SQL  
  
1. В Visual Studio в меню **файл** наведите указатель мыши на пункт **создать** и выберите **проект**. Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.  
  
2. В меню **Проект** выберите **Добавить новый элемент**. Выберите шаблон элемента **LINQ to SQL классы** .  
  
3. Задайте файлу имя `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Добавление хранимых процедур в реляционный конструктор O/R  
  
1. В **Обозреватель сервера** / **Обозреватель базы данных**разверните подключение к базе данных Northwind. Разверните папку **Хранимые процедуры** .  
  
     Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.  
  
2. Щелкните хранимую процедуру **продажи по году** и перетащите ее на правую панель конструктора. Щелкните **десять самых дорогих** хранимых процедур продуктов, перетащите ее на правую панель конструктора.  
  
3. Сохраните изменения и закройте конструктор.  
  
4. Сохраните проект.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Добавление кода для вывода результатов хранимых процедур  
  
1. Перетащите элемент управления из **области элементов**в <xref:System.Windows.Forms.DataGridView> форму Windows по умолчанию для проекта, Form1.  
  
2. Дважды щелкните Form1, чтобы добавить код к `Load` событию.  
  
3. При добавлении хранимых процедур в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объект для проекта. Этот объект содержит код, который необходим для доступа к этим процедурам. Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла. Для этого проекта объект называется <xref:System.Data.Linq.DataContext> `northwindDataContext` .  
  
     В коде можно создать экземпляр класса <xref:System.Data.Linq.DataContext> и вызвать методы хранимой процедуры, заданные в конструкторе O/R. Чтобы выполнить привязку к <xref:System.Windows.Forms.DataGridView> объекту, может потребоваться принудительно выполнить запрос, вызвав <xref:System.Linq.Enumerable.ToList%2A> метод для результатов хранимой процедуры.  
  
     Добавьте следующий код в `Load` событие для вызова любой из хранимых процедур, предоставляемых как методы для контекста данных.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также раздел

- [LINQ](index.md)
- [Запросы](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор R)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
