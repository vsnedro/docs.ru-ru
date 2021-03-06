---
title: Разбивка на страницы результатов запроса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 065b509d8385ee37b2a86587f520b5fd3207ceff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186956"
---
# <a name="paging-through-a-query-result"></a>Разбивка на страницы результатов запроса

Постраничный просмотр результатов запроса - это процесс возврата результатов запроса небольшими подмножествами данных (страницами). Этот метод часто используется для вывода результатов пользователю в виде небольших фрагментов, с которыми легко работать.  
  
 **DataAdapter** предоставляет средство для возвращения только страницы данных с помощью перегрузок метода **Fill** . Однако это может быть не лучшим выбором для разбиения на страницы больших результатов запроса, поскольку, хотя **DataAdapter** заполняет целевой объект <xref:System.Data.DataTable> или <xref:System.Data.DataSet> только запрошенными записями, все еще используются ресурсы для возврата всего запроса. Для возврата страницы данных из источника данных без использования лишних ресурсов задайте для запроса дополнительные критерии, которые ограничат число возвращаемых строки только необходимыми.  
  
 Чтобы использовать метод **Fill** для возврата страницы данных, укажите параметр **startRecord** для первой записи на странице данных и параметр **maxRecords** для количества записей на странице данных.  
  
 В следующем примере кода показано, как использовать метод **Fill** для возврата первой страницы результата запроса, в котором размер страницы составляет пять записей.  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 В предыдущем примере **набор данных** заполняется только пятью записями, но возвращается вся таблица **Orders** . Чтобы заполнить **набор данных** теми же пятью записями, но возвращать только пять записей, используйте предложения TOP и WHERE в инструкции SQL, как показано в следующем примере кода.  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 Обратите внимание, что при таком способе постраничного просмотра результатов запроса необходимо сохранять уникальный идентификатор, с помощью которого выполняется упорядочение строк. Этот уникальный идентификатор нужно будет передать команде, служащей для возврата следующей страницы записей, как показано в следующем примере кода.  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 Чтобы вернуть следующую страницу записей с помощью перегрузки метода **Fill** , который принимает параметры **startRecord** и **maxRecords** , увеличьте индекс текущей записи по размеру страницы и заполните таблицу. Помните, что сервер базы данных возвращает все результаты запроса, несмотря на то, что в **набор данных**добавляется только одна страница записей. В следующем примере кода строки таблицы очищаются, а затем заполняются следующей страницей данных. Может быть необходимым сохранить определенное число возвращенных строк в локальном кэше, чтобы уменьшить число обращений к серверу базы данных.  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 Чтобы возвратить следующую страницу записей, не заставляя сервер баз данных возвращать сразу все результаты запроса, укажите ограничивающие критерии для инструкции SELECT. Так как код предыдущего примера сохранил последнюю возвращенную запись, ее можно использовать в предложении WHERE, чтобы указать для запроса начальную точку, как показано в следующем примере кода.  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a>См. также раздел

- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
