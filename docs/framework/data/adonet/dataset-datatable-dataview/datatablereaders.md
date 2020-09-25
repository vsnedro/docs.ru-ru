---
title: Объекты DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 911a45dad3d5d82ab5e5752b1c12f7d8a6ab1563
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202322"
---
# <a name="datatablereaders"></a>Объекты DataTableReader

<xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.  
  
 При создании объекта **DataTableReader** из **таблицы**данных результирующий объект **DataTableReader** содержит один результирующий набор с теми же данными, что и **таблица DataTable** , из которой он был создан, за исключением строк, которые были помечены как удаленные. Столбцы отображаются в том же порядке, что и в исходной **таблице**данных.  
  
 Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан путем вызова метода <xref:System.Data.DataSet.CreateDataReader%2A> . Результаты находятся в том же порядке, что и **DataTables** в коллекции объекта **DataSet** <xref:System.Data.DataSet.Tables%2A> .  
  
## <a name="in-this-section"></a>в этом разделе  

 [Создание объекта DataReader](creating-a-datareader.md)  
 Описывает, как создать объект **DataTableReader** .  
  
 [Навигация по таблицам данных](navigating-datatables.md)  
 Описывает использование метода **Read** для перемещения по содержимому объекта **DataTableReader**.  
  
## <a name="see-also"></a>См. также раздел

- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
