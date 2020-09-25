---
title: Практическое руководство. Как указать типы данных базы данных
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: f070ff718ac10b9681c5ab3c0f4b46547349101b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197239"
---
# <a name="how-to-specify-database-data-types"></a>Практическое руководство. Как указать типы данных базы данных

Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута, чтобы указать точный текст, определяющий столбец в объявлении таблицы T-SQL.  
  
 Свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> следует задавать, только если для создания экземпляра базы данных планируется использовать <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>Задание текста для определения типа данных в таблице T-SQL  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. В качестве значения свойства <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> укажите точный текст, используемый T-SQL.  
  
## <a name="see-also"></a>См. также раздел

- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Практическое руководство. Как настроить классы сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
