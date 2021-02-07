---
description: 'Дополнительные сведения: Загрузка данных в набор данных'
title: Загрузка данных в набор данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 167a399d17257008e884fbcccc96de17398b8f88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681686"
---
# <a name="loading-data-into-a-dataset"></a>Загрузка данных в набор данных

<xref:System.Data.DataSet>Прежде чем можно будет выполнить запрос к нему с помощью LINQ to DataSet, сначала необходимо заполнить объект. Существует несколько способов заполнения объекта <xref:System.Data.DataSet>. Например, можно использовать [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] для запроса базы данных и загрузки результатов в <xref:System.Data.DataSet> . Дополнительные сведения см. в разделе [LINQ to SQL](./sql/linq/index.md).  
  
 Другой распространенный способ загрузки данных в объект <xref:System.Data.DataSet> - использование класса <xref:System.Data.Common.DataAdapter> для получения данных из базы данных. Это продемонстрировано в следующем примере.  
  
## <a name="example"></a>Пример  

 В этом примере объект <xref:System.Data.Common.DataAdapter> используется для запроса к базе данных AdventureWorks, получения сведений о продажах начиная с 2002 года и загрузки результатов в объект <xref:System.Data.DataSet>. После <xref:System.Data.DataSet> заполнения можно создавать запросы к нему с помощью LINQ to DataSet. `FillDataSet`Метод в этом примере используется в примерах запросов в [LINQ to DataSet примерах](linq-to-dataset-examples.md). Дополнительные сведения см. в разделе [запросы к наборам данных](querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о LINQ to DataSet](linq-to-dataset-overview.md)
- [Запросы к DataSet](querying-datasets-linq-to-dataset.md)
- [Примеры LINQ to DataSet](linq-to-dataset-examples.md)
