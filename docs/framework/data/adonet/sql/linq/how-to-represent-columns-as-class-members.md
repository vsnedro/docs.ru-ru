---
title: Практическое руководство. Как представить столбцы в виде членов класса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: e73b017b5a500a8c48b3fe22557f6c6619f3b227
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166356"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="33fd5-102">Практическое руководство. Как представить столбцы в виде членов класса</span><span class="sxs-lookup"><span data-stu-id="33fd5-102">How to: Represent Columns as Class Members</span></span>

<span data-ttu-id="33fd5-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут, чтобы связать поле или свойство со столбцом базы данных.</span><span class="sxs-lookup"><span data-stu-id="33fd5-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="33fd5-104">Сопоставление поля или свойства со столбцом база данных</span><span class="sxs-lookup"><span data-stu-id="33fd5-104">To map a field or property to a database column</span></span>  
  
- <span data-ttu-id="33fd5-105">Добавьте атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute> в объявление свойства или поля.</span><span class="sxs-lookup"><span data-stu-id="33fd5-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33fd5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="33fd5-106">Example</span></span>  

 <span data-ttu-id="33fd5-107">В следующем коде поле `CustomerID` в классе `Customer` сопоставляется со столбцом `CustomerID` в таблице базы данных `Customers`.</span><span class="sxs-lookup"><span data-stu-id="33fd5-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="33fd5-108">Если можно определить имя, указывать свойство <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="33fd5-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="33fd5-109">Если имя не указано, оно будет считаться совпадающим с именем свойства или поля.</span><span class="sxs-lookup"><span data-stu-id="33fd5-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33fd5-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="33fd5-110">See also</span></span>

- [<span data-ttu-id="33fd5-111">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="33fd5-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="33fd5-112">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="33fd5-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
