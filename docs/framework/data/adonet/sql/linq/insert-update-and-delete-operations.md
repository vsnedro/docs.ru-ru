---
description: 'Дополнительные сведения: операции вставки, обновления и удаления'
title: Операции вставки, обновления и удаления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: 2d0470ed6abe654ca08f954c3de97de207adb75d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803822"
---
# <a name="insert-update-and-delete-operations"></a>Операции вставки, обновления и удаления

В `Insert` операции `Update`, `Delete` и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняются путем добавления, изменения и удаления объектов в объектной модели. По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует действия в язык SQL и отправляет изменения в базу данных.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обеспечивает максимальную гибкость при манипуляции и сохранении изменений, внесенных в объекты. Как только будут доступны объекты сущности (либо при извлечении их с помощью запроса, либо при создании заново), их можно изменить как обычные объекты в приложении. Это означает, что можно изменить их значения, добавить в коллекцию или удалить из нее. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отслеживает изменения и готов отправить их обратно в базу данных, когда будет вызван метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.

> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления. Если необходимо удалить строку в таблице с ограничениями, необходимо либо задать `ON DELETE CASCADE` правило в ограничении внешнего ключа в базе данных, либо использовать собственный код, чтобы сначала удалить дочерние объекты, препятствующие удалению родительского объекта. В противном случае создается исключение. Дополнительные сведения см. в разделе [инструкции. Удаление строк из базы данных](how-to-delete-rows-from-the-database.md).

В следующих фрагментах используются классы `Customer` и `Order` из образца базы данных "Борей". Для краткости определения классов не показаны.

[!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
[!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]

При вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] автоматически создает и выполняет команды SQL, необходимые для передачи изменений обратно в базу данных.

> [!NOTE]
> Это поведение можно переопределить использованием собственной настраиваемой логики, обычно за счет хранимой процедуры. Дополнительные сведения см. [в разделе обязанности разработчика при переопределении поведения по умолчанию](responsibilities-of-the-developer-in-overriding-default-behavior.md).
>
> Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для разработки хранимых процедур для этой цели.

## <a name="see-also"></a>См. также

- [Загрузка примеров баз данных](downloading-sample-databases.md)
- [Настройка операций вставки, обновления и удаления](customizing-insert-update-and-delete-operations.md)
