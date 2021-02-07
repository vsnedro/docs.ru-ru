---
description: Дополнительные сведения о том, как представлять первичные ключи.
title: Практическое руководство. Как представить первичные ключи
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 1fbac2d60bd730718b5330bfd48910a61deae15c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723612"
---
# <a name="how-to-represent-primary-keys"></a>Практическое руководство. Как представить первичные ключи

Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута, чтобы назначить свойство или поле для представления первичного ключа столбца базы данных.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает вычисляемые столбцы в качестве первичных ключей.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>Назначение свойства или поля в качестве первичного ключа  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. В качестве значения задайте `true`.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Практическое руководство. Как настроить классы сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
