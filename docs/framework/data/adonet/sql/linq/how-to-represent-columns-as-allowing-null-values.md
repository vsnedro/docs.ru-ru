---
title: Практическое руководство. Как представлять столбцы, допускающие значения NULL
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: ec88429ed9c1f91917476cc807bd6b53f0bcc3a3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166369"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="50c42-102">Практическое руководство. Как представлять столбцы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="50c42-102">How to: Represent Columns as Allowing Null Values</span></span>

<span data-ttu-id="50c42-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута, чтобы указать, что в связанном столбце базы данных могут храниться значения NULL.</span><span class="sxs-lookup"><span data-stu-id="50c42-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="50c42-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="50c42-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="50c42-105">Включение для столбца возможности содержать значения NULL</span><span class="sxs-lookup"><span data-stu-id="50c42-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="50c42-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="50c42-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="50c42-107">Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="50c42-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c42-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="50c42-108">See also</span></span>

- [<span data-ttu-id="50c42-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="50c42-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="50c42-110">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="50c42-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
