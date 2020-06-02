---
title: Практическое руководство. Как удалить строки из базы данных
description: Сведения об удалении строк в базе данных путем удаления объектов LINQ to SQL из коллекции, связанной с таблицами. LINQ to SQL преобразует удаления в команды SQL DELETE.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: d08621e834961e1db9312cac36bd2e69133142b5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286395"
---
# <a name="how-to-delete-rows-from-the-database"></a>Практическое руководство. Как удалить строки из базы данных

Можно удалить строки в базе данных, удалив соответствующие [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объекты из их коллекции, связанной с таблицами. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]преобразует изменения в соответствующие `DELETE` команды SQL.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления. Если требуется удалить строку в таблице, имеющей ограничения, необходимо выполнить любую из следующих задач.

- Установите правило `ON DELETE CASCADE` в ограничении внешнего ключа в базе данных.

- Используйте собственный код, чтобы сначала удалить дочерние объекты, не допускающие удаление родительского объекта.

 В противном случае создается исключение. См. второй пример кода далее в этом разделе.

> [!NOTE]
> Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных. Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](customizing-insert-update-and-delete-operations.md).
>
> Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для разработки хранимых процедур для той же цели.

В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>. Дополнительные сведения см. в разделе [как подключиться к базе данных](how-to-connect-to-a-database.md).

### <a name="to-delete-a-row-in-the-database"></a>Удаление строки в базе данных

1. Отправьте в базу данных запрос на удаляемую строку.

2. Вызовите метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> .

3. Отправьте изменение в базу данных.

## <a name="example"></a>Пример

В первом примере кода в базу данных отправляется запрос на сведения о заказе "Order #11000", помечаются сведения для удаления, а изменения отправляются в базу данных.

[!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
[!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]

## <a name="example"></a>Пример

Целью второго примера является удаление заказа (с номером 10250). Код сначала проверяет таблицу `OrderDetails` на наличие в ней дочерних элементов удаляемого заказа. Если в таблице есть дочерние элементы заказа, сначала они, а затем сам заказ помечаются для удаления. <xref:System.Data.Linq.DataContext> располагает фактические действия по удалению в надлежащей последовательности, чтобы команды удаления, отправляемые в базу данных, подчинялись ее ограничениям.

[!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
[!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]

## <a name="see-also"></a>См. также

- [Практическое руководство. Как управлять конфликтами изменений](how-to-manage-change-conflicts.md)
- [Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Внесение и отправка изменений данных](making-and-submitting-data-changes.md)
