---
title: Практическое руководство. Как представить первичные ключи
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 02570176c8aef5cfdc7ba09fd6976f430900e8df
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166239"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="adb24-102">Практическое руководство. Как представить первичные ключи</span><span class="sxs-lookup"><span data-stu-id="adb24-102">How to: Represent Primary Keys</span></span>

<span data-ttu-id="adb24-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута, чтобы назначить свойство или поле для представления первичного ключа столбца базы данных.</span><span class="sxs-lookup"><span data-stu-id="adb24-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="adb24-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="adb24-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="adb24-105">не поддерживает вычисляемые столбцы в качестве первичных ключей.</span><span class="sxs-lookup"><span data-stu-id="adb24-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="adb24-106">Назначение свойства или поля в качестве первичного ключа</span><span class="sxs-lookup"><span data-stu-id="adb24-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="adb24-107">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="adb24-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="adb24-108">В качестве значения задайте `true`.</span><span class="sxs-lookup"><span data-stu-id="adb24-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb24-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="adb24-109">See also</span></span>

- [<span data-ttu-id="adb24-110">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="adb24-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="adb24-111">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="adb24-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
