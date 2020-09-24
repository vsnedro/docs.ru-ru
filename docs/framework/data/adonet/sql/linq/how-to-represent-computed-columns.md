---
title: Практическое руководство. Как представить вычисляемые столбцы
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: d952a6c22cd96bbc89aeebfa4b13e9727a363c73
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166330"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="2a9aa-102">Практическое руководство. Как представить вычисляемые столбцы</span><span class="sxs-lookup"><span data-stu-id="2a9aa-102">How to: Represent Computed Columns</span></span>

<span data-ttu-id="2a9aa-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута для представления столбца, содержимое которого является результатом вычисления.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="2a9aa-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="2a9aa-105">не поддерживает вычисляемые столбцы в качестве первичных ключей.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="2a9aa-106">Представление вычисляемого столбца</span><span class="sxs-lookup"><span data-stu-id="2a9aa-106">To represent a computed column</span></span>  
  
1. <span data-ttu-id="2a9aa-107">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="2a9aa-108">Присвойте атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> строковое представление формулы.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9aa-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a9aa-109">See also</span></span>

- [<span data-ttu-id="2a9aa-110">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2a9aa-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="2a9aa-111">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="2a9aa-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
