---
description: Дополнительные сведения см. в статье как указать закрытые поля хранилища
title: Практическое руководство. Как указать поля закрытого хранения
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: 09f3566ca85a69f27794329ae12fc45d88bb518c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785904"
---
# <a name="how-to-specify-private-storage-fields"></a>Практическое руководство. Как указать поля закрытого хранения

Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> свойство <xref:System.Data.Linq.Mapping.DataAttribute> атрибута для обозначения имени базового поля хранилища.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a>Задание имени базового поля хранения  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Укажите имя поля в качестве значения свойства <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Практическое руководство. Как настроить классы сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
