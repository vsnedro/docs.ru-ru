---
title: Практическое руководство. Как представить таблицы в виде классов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: c02922351909b097dc06085eefbcc0f131350505
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166226"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="faad9-102">Практическое руководство. Как представить таблицы в виде классов</span><span class="sxs-lookup"><span data-stu-id="faad9-102">How to: Represent Tables as Classes</span></span>

<span data-ttu-id="faad9-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> атрибут, чтобы назначить класс как класс сущности, связанный с таблицей базы данных.</span><span class="sxs-lookup"><span data-stu-id="faad9-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="faad9-104">Сопоставление класса с таблицей базы данных</span><span class="sxs-lookup"><span data-stu-id="faad9-104">To map a class to a database table</span></span>  
  
- <span data-ttu-id="faad9-105">Добавьте в объявление класса атрибут <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="faad9-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="faad9-106">Пример</span><span class="sxs-lookup"><span data-stu-id="faad9-106">Example</span></span>  

 <span data-ttu-id="faad9-107">Следующий код определяет класс `Customer` как класс сущности, связанный с таблицей базы данных `Customers`.</span><span class="sxs-lookup"><span data-stu-id="faad9-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="faad9-108">Если можно определить имя, указывать свойство <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="faad9-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="faad9-109">Если имя не указано, оно будет считаться совпадающим с именем свойства или поля.</span><span class="sxs-lookup"><span data-stu-id="faad9-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faad9-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="faad9-110">See also</span></span>

- [<span data-ttu-id="faad9-111">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="faad9-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="faad9-112">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="faad9-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
