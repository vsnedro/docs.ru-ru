---
title: Создание объекта DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 3af6ae3a8f4ecc3ec34c186ce55c1c77c27514a9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202336"
---
# <a name="creating-a-datareader"></a>Создание объекта DataReader

Классы <xref:System.Data.DataTable> и <xref:System.Data.DataSet> имеют метод <xref:System.Data.DataTable.CreateDataReader%2A>, возвращающий содержимое объекта <xref:System.Data.DataTable> или содержимое объекта <xref:System.Data.DataSet> коллекции <xref:System.Data.DataSet.Tables%2A> в виде одного или нескольких доступных для чтения результирующих наборов с последовательным доступом.  
  
## <a name="example"></a>Пример  

 Следующее приложение командной строки создает экземпляр <xref:System.Data.DataTable>. Затем в примере передается заполненная <xref:System.Data.DataTable> процедура, которая вызывает <xref:System.Data.DataTable.CreateDataReader%2A> метод, который выполняет итерацию по результатам, содержащимся в <xref:System.Data.DataTableReader> .  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 В этом примере в окне консоли отображаются следующие выходные данные:  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [Объекты DataTableReader](datatablereaders.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
