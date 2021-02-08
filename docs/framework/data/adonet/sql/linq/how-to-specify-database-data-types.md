---
description: Дополнительные сведения см. в статье как указать типы данных базы данных
title: Практическое руководство. Как указать типы данных базы данных
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 004a16fe9dd0cda608485b13b03ce922d6a9f671
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785917"
---
# <a name="how-to-specify-database-data-types"></a>Практическое руководство. Как указать типы данных базы данных

Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута, чтобы указать точный текст, определяющий столбец в объявлении таблицы T-SQL.  
  
 Свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> следует задавать, только если для создания экземпляра базы данных планируется использовать <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>Задание текста для определения типа данных в таблице T-SQL  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. В качестве значения свойства <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> укажите точный текст, используемый T-SQL.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Практическое руководство. Как настроить классы сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
