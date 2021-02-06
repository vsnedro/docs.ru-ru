---
description: 'Дополнительные сведения о: Дататаблереадерс'
title: Объекты DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: b3e85ae05c07af18fe6219602b5b40f50a9fbc8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652605"
---
# <a name="datatablereaders"></a>Объекты DataTableReader

<xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.  
  
 При создании объекта **DataTableReader** из **таблицы** данных результирующий объект **DataTableReader** содержит один результирующий набор с теми же данными, что и **таблица DataTable** , из которой он был создан, за исключением строк, которые были помечены как удаленные. Столбцы отображаются в том же порядке, что и в исходной **таблице** данных.  
  
 Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан путем вызова метода <xref:System.Data.DataSet.CreateDataReader%2A> . Результаты находятся в том же порядке, что и **DataTables** в коллекции объекта **DataSet** <xref:System.Data.DataSet.Tables%2A> .  
  
## <a name="in-this-section"></a>В этом разделе  

 [Создание объекта DataReader](creating-a-datareader.md)  
 Описывает, как создать объект **DataTableReader** .  
  
 [Навигация по таблицам данных](navigating-datatables.md)  
 Описывает использование метода **Read** для перемещения по содержимому объекта **DataTableReader**.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
