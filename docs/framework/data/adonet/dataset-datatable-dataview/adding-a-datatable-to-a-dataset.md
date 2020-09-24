---
title: Добавление новой таблицы данных в набор данных
description: Ознакомьтесь с этим примером кода, чтобы узнать, как создавать объекты DataTable и добавлять их в существующий набор данных в ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 6a5e3a89870b3959a6ac042b93414694e8a6cc1c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164900"
---
# <a name="adding-a-datatable-to-a-dataset"></a>Добавление новой таблицы данных в набор данных

ADO.NET позволяет создавать объекты <xref:System.Data.DataTable> и добавлять их к существующему <xref:System.Data.DataSet>. Можно задать данные ограничения для <xref:System.Data.DataTable>, используя свойства <xref:System.Data.DataTable.PrimaryKey%2A> и <xref:System.Data.DataColumn.Unique%2A>.  
  
## <a name="example"></a>Пример  

 Следующий пример показывает, как создать объект <xref:System.Data.DataSet>, добавить новый объект <xref:System.Data.DataTable> к <xref:System.Data.DataSet>, а затем добавить к таблице три объекта <xref:System.Data.DataColumn>. В конце код задает один столбец в качестве столбца первичного ключа.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a>Чувствительность к регистру  

 В <xref:System.Data.DataSet> могут существовать две или несколько таблиц или связей, имеющие одинаковые имена, которые, тем не менее, состоят из символов с разными регистрами. В таких случаях ссылки по имени на таблицы и связи задаются с учетом регистра. Например, если <xref:System.Data.DataSet> **набор данных** содержит таблицы **Table1** и **Table1**, вы бы ссылались на таблицу **Table1** по имени как **DataSet. Tables ["table1"]** и **Table1** в качестве **набора данных. Tables ["table1"]**. Попытка ссылки на любую из таблиц в качестве **набора данных. таблицы ["table1"]** создают исключение.  
  
 Это правило учета регистра не применяется, если только одна таблица или связь имеет какое-то определенное имя. Например, если <xref:System.Data.DataSet> имеет только **Таблица1**, можно ссылаться на него с помощью **DataSet. Tables ["table1"]**.  
  
> [!NOTE]
> Указанное правило применяется без учета значения свойства <xref:System.Data.DataSet.CaseSensitive%2A> объекта <xref:System.Data.DataSet>. Свойство <xref:System.Data.DataSet.CaseSensitive%2A> применяется к данным в <xref:System.Data.DataSet> и затрагивает сортировку, поиск, фильтрацию, предписание ограничений и т. д.  
  
## <a name="namespace-support"></a>Поддержка пространства имен  

 В версиях ADO.NET, выпущенных до версии 2.0, две таблицы не могли иметь одинаковое имя, даже если находились в разных пространствах имен. Это ограничение было снято в ADO.NET 2.0. Набор данных <xref:System.Data.DataSet> может содержать две таблицы, имеющие одинаковое значение свойства <xref:System.Data.DataTable.TableName%2A>, но различные значения свойства <xref:System.Data.DataTable.Namespace%2A>.  
  
## <a name="see-also"></a>См. также раздел

- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
