---
title: Добавление бизнес-логики с использованием разделяемых методов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 9ad3329c621b8bf8eaa0fd5f986ac7e8cff97d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156164"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="71cb3-102">Добавление бизнес-логики с использованием разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="71cb3-102">Adding Business Logic By Using Partial Methods</span></span>

<span data-ttu-id="71cb3-103">Можно настроить Visual Basic и код, созданный C#, в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проектах с помощью *разделяемых методов*.</span><span class="sxs-lookup"><span data-stu-id="71cb3-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="71cb3-104">Код, созданный [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], определяет сигнатуры как одну часть разделяемого метода.</span><span class="sxs-lookup"><span data-stu-id="71cb3-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="71cb3-105">Если необходимо реализовать метод, можно добавить собственный разделяемый метод.</span><span class="sxs-lookup"><span data-stu-id="71cb3-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="71cb3-106">Если собственная реализация не добавляется, компилятор отменяет сигнатуру разделяемых методов и вызывает в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] методы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71cb3-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71cb3-107">При использовании Visual Studio можно использовать реляционный конструктор объектов для добавления проверки и других настроек в классы сущностей.</span><span class="sxs-lookup"><span data-stu-id="71cb3-107">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="71cb3-108">Например, применяемое по умолчанию сопоставление для класса `Customer` в образце базы данных Northwind включает следующий разделяемый метод:</span><span class="sxs-lookup"><span data-stu-id="71cb3-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="71cb3-109">Можно реализовать собственный метод путем добавления кода, подобного представленному далее, в собственный разделяемый класс `Customer`.</span><span class="sxs-lookup"><span data-stu-id="71cb3-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="71cb3-110">Этот подход обычно используется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для переопределения методов по умолчанию для `Insert` ,, и `Update` `Delete` для проверки свойств во время событий жизненного цикла объекта.</span><span class="sxs-lookup"><span data-stu-id="71cb3-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="71cb3-111">Дополнительные сведения см. в разделе [разделяемые методы](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) или [partial (метод) (Справочник по c#](../../../../../csharp/language-reference/keywords/partial-method.md) ) (c#).</span><span class="sxs-lookup"><span data-stu-id="71cb3-111">For more information, see [Partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71cb3-112">Пример</span><span class="sxs-lookup"><span data-stu-id="71cb3-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="71cb3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="71cb3-113">Description</span></span>  

 <span data-ttu-id="71cb3-114">В примере кода `ExampleClass` сначала отображается так, как если бы он был определен с помощью средства создания кода, например SQLMetal, а затем так, как при реализации только одного из двух методов.</span><span class="sxs-lookup"><span data-stu-id="71cb3-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="71cb3-115">Код</span><span class="sxs-lookup"><span data-stu-id="71cb3-115">Code</span></span>  

 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="71cb3-116">Пример</span><span class="sxs-lookup"><span data-stu-id="71cb3-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="71cb3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="71cb3-117">Description</span></span>  

 <span data-ttu-id="71cb3-118">В следующем примере используется связь между сущностями `Shipper` и `Order`.</span><span class="sxs-lookup"><span data-stu-id="71cb3-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="71cb3-119">Среди прочих методов обратите внимание на разделяемые - `InsertShipper` и `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="71cb3-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="71cb3-120">Эти методы переопределяют разделяемые методы по умолчанию, предоставляемые [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставлением.</span><span class="sxs-lookup"><span data-stu-id="71cb3-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="71cb3-121">Код</span><span class="sxs-lookup"><span data-stu-id="71cb3-121">Code</span></span>  

 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="71cb3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="71cb3-122">See also</span></span>

- [<span data-ttu-id="71cb3-123">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="71cb3-123">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="71cb3-124">Настройка операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="71cb3-124">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
