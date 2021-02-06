---
description: 'Дополнительные сведения: Просмотр данных в DataTable'
title: Просмотр данных в таблице данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: ffaa8283da17c98fc58486af8dad741a61bbafc8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651383"
---
# <a name="viewing-data-in-a-datatable"></a>Просмотр данных в таблице данных

Доступ к содержимому объекта можно получить с <xref:System.Data.DataTable> помощью коллекций **Rows** и **Columns** **таблицы DataTable**. Также можно использовать метод, <xref:System.Data.DataTable.Select%2A> чтобы возвращать подмножества данных в **DataTable** в соответствии с критериями, в том числе критериями поиска, порядком сортировки и состоянием строк. Кроме того, можно использовать <xref:System.Data.DataRowCollection.Find%2A> метод **датаровколлектион** при поиске определенной строки с помощью значения первичного ключа.

Метод **SELECT** объекта **DataTable** возвращает набор <xref:System.Data.DataRow> объектов, соответствующих указанным критериям. **SELECT** принимает необязательные аргументы критерия фильтра, выражения сортировки и **DataViewRowState**. Выражение фильтра определяет, какие строки должны возвращаться на основе значений **DataColumn** , таких как `LastName = 'Smith'` . Выражение сортировки следует стандартным соглашениям SQL об упорядочивании столбцов, например по `LastName ASC, FirstName ASC`. Правила написания выражений см. в описании <xref:System.Data.DataColumn.Expression%2A> Свойства класса **DataColumn** .

> [!TIP]
> При выполнении нескольких вызовов к методу **SELECT** объекта **DataTable** можно повысить производительность, создавая <xref:System.Data.DataView> для **таблицы DataTable**. При создании объект **DataView** индексирует строки таблицы. Затем метод **SELECT** использует этот индекс, что значительно сокращает время создания результата запроса. Дополнительные сведения о создании **DataView** для **DataTable** см. в разделе « [представления](dataviews.md)данных».

Метод **SELECT** определяет версию строк для просмотра или управления на основе <xref:System.Data.DataViewRowState> . В следующей таблице описаны возможные значения перечисления **DataViewRowState** .

|Значение DataViewRowState|Описание|
|----------------------------|-----------------|
|**CurrentRows**|Текущие строки, включая не изменившиеся, добавленные и измененные.|
|**Удалено**|Удаленная строка.|
|**ModifiedCurrent**|Текущая версия, которая является измененной версией исходных данных. (См. **модифиедоригинал**.)|
|**ModifiedOriginal**|Исходная версия всех измененных строк. Текущая версия доступна с помощью **модифиедкуррент**.|
|**Добавлено**|Новая строка.|
|**Нет**|Отсутствует.|
|**OriginalRows**|Исходные строки, включая неизменившиеся и удаленные.|
|**Без изменений**|Неизменившаяся строка.|

В следующем примере объект **DataSet** фильтруется так, что вы работаете только со строками, для которых для **DataViewRowState** задано значение **куррентровс**.

```vb
Dim column As DataColumn
Dim row As DataRow

Dim currentRows() As DataRow = _
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)

If (currentRows.Length < 1 ) Then
  Console.WriteLine("No Current Rows Found")
Else
  For Each column in workTable.Columns
    Console.Write(vbTab & column.ColumnName)
  Next

  Console.WriteLine(vbTab & "RowState")

  For Each row In currentRows
    For Each column In workTable.Columns
      Console.Write(vbTab & row(column).ToString())
    Next

    Dim rowState As String = _
        System.Enum.GetName(row.RowState.GetType(), row.RowState)
    Console.WriteLine(vbTab & rowState)
  Next
End If
```

```csharp
DataRow[] currentRows = workTable.Select(
    null, null, DataViewRowState.CurrentRows);

if (currentRows.Length < 1 )
  Console.WriteLine("No Current Rows Found");
else
{
  foreach (DataColumn column in workTable.Columns)
    Console.Write("\t{0}", column.ColumnName);

  Console.WriteLine("\tRowState");

  foreach (DataRow row in currentRows)
  {
    foreach (DataColumn column in workTable.Columns)
      Console.Write("\t{0}", row[column]);

    Console.WriteLine("\t" + row.RowState);
  }
}
```

Метод **SELECT** можно использовать для возврата строк с разными значениями **RowState** или значениями полей. В следующем примере возвращается массив **DataRow** , который ссылается на все удаленные строки, и возвращается другой массив **DataRow** , который ссылается на все строки, упорядоченные по **кустлнаме**, где столбец **CustID** больше 5. Сведения о просмотре сведений в **удаленной** строке см. в разделе [состояния строк и версии строк](row-states-and-row-versions.md).

```vb
' Retrieve all deleted rows.
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)

' Retrieve rows where CustID > 5, and order by CustLName.
Dim custRows() As DataRow = workTable.Select( _
    "CustID > 5", "CustLName ASC")
```

```csharp
// Retrieve all deleted rows.
DataRow[] deletedRows = workTable.Select(
    null, null, DataViewRowState.Deleted);

// Retrieve rows where CustID > 5, and order by CustLName.
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");
```

## <a name="see-also"></a>См. также

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [Управление данными в таблице данных](manipulating-data-in-a-datatable.md)
- [Состояния и версии строк](row-states-and-row-versions.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
