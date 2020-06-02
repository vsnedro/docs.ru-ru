---
title: Практическое руководство. Как вставить строки в базу данных
description: Сведения о вставке строк в базу данных путем добавления LINQ to SQL объектов в коллекцию, связанную с таблицей. LINQ to SQL преобразует дополнения в команды SQL INSERT.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 39eee6edf59d2adb7de41efd88899050fbe69fd8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286356"
---
# <a name="how-to-insert-rows-into-the-database"></a>Практическое руководство. Как вставить строки в базу данных

Строки вставляются в базу данных путем добавления объектов в связанную [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> коллекцию и последующей отправки изменений в базу данных. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]преобразует изменения в соответствующие `INSERT` команды SQL.

> [!NOTE]
> Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных. Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](customizing-insert-update-and-delete-operations.md).
>
> Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для разработки хранимых процедур для той же цели.

В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>. Дополнительные сведения см. в разделе [как подключиться к базе данных](how-to-connect-to-a-database.md).

### <a name="to-insert-a-row-into-the-database"></a>Вставка строки в базу данных

1. Создайте новый объект, содержащий столбец данных для отправки.

2. Добавьте новый объект в коллекцию, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` связанную с целевой таблицей в базе данных.

3. Отправьте изменение в базу данных.

## <a name="example"></a>Пример

В следующем примере кода создается новый объект с типом `Order` и заполняется соответствующими значениями. Затем новый объект добавляется в коллекцию `Order`. И наконец, изменение отправляется в базу данных в виде новой строки в таблице`Orders`.

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a>См. также

- [Практическое руководство. Как управлять конфликтами изменений](how-to-manage-change-conflicts.md)
- [Методы DataContext (реляционный конструктор R)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Внесение и отправка изменений данных](making-and-submitting-data-changes.md)
