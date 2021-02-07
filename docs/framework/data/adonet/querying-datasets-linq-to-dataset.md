---
description: 'Дополнительные сведения: запросы к наборам данных (LINQ to DataSet)'
title: Запросы к наборам данных (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 609de99069d39317d8d372cb2a7f43ea301ada2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663460"
---
# <a name="querying-datasets-linq-to-dataset"></a>Запросы к наборам данных (LINQ to DataSet)

После того как в объекте <xref:System.Data.DataSet> появятся данные, к нему можно выполнять запросы. Запросы составления с LINQ to DataSet похожи на использование Language-Integrated query (LINQ) с другими источниками данных, поддерживающими LINQ. Однако помните, что при использовании запросов LINQ через <xref:System.Data.DataSet> объект выполняется запрос перечисления <xref:System.Data.DataRow> объектов вместо перечисления настраиваемого типа. Это означает, что вы можете использовать любой из членов <xref:System.Data.DataRow> класса в запросах LINQ. Это позволяет создавать сложные сложных запросы.  
  
 Как и в других реализациях LINQ, запросы LINQ to DataSet можно создавать в двух разных формах: синтаксис выражений запроса и синтаксис запросов на основе методов. Синтаксис выражений запросов или синтаксис запросов на основе методов можно использовать для выполнения запросов к отдельным таблицам в <xref:System.Data.DataSet>, к нескольким таблицам в <xref:System.Data.DataSet> или к таблицам в типизированном <xref:System.Data.DataSet>.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Запросы к одной таблице](single-table-queries-linq-to-dataset.md)  
 Описывается выполнение запросов к отдельным таблицам.  
  
 [Запросы между таблицами](cross-table-queries-linq-to-dataset.md)  
 Описывается выполнение межтабличных запросов.  
  
 [Запрос к типизированным объектам DataSet](querying-typed-datasets.md)  
 Описываются запросы к типизированным объектам <xref:System.Data.DataSet>.  
  
## <a name="see-also"></a>См. также

- [Примеры LINQ to DataSet](linq-to-dataset-examples.md)
- [Загрузка данных в набор данных](loading-data-into-a-dataset.md)
