---
description: Дополнительные сведения см. в статье как представить столбцы как Database-Generated
title: Практическое руководство. Как представить столбцы как сформированные базой данных
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 01828ef3f73257d20023168f0ea471ee7e3863c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695636"
---
# <a name="how-to-represent-columns-as-database-generated"></a>Практическое руководство. Как представить столбцы как сформированные базой данных

Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута для обозначения поля или свойства, представляющего столбец, сформированный базой данных.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a>Назначение поля или свойства, представляющего столбец, созданный базой данных  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. В качестве значения свойства задайте `true`.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Практическое руководство. Как настроить классы сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
