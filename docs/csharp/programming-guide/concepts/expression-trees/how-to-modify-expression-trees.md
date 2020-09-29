---
title: Практическое руководство. Изменение деревьев выражений (C#)
description: Узнайте, как изменить дерево выражения путем создания копии существующего дерева выражения и внесения необходимых изменений.
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 01176f489794a0f4ca29d229d29507fdba0fd5a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167695"
---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="409c4-103">Практическое руководство. Изменение деревьев выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="409c4-103">How to modify expression trees (C#)</span></span>

<span data-ttu-id="409c4-104">В этом разделе показано, как изменить дерево выражения.</span><span class="sxs-lookup"><span data-stu-id="409c4-104">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="409c4-105">Деревья выражений являются неизменяемыми, что означает невозможность их изменения напрямую.</span><span class="sxs-lookup"><span data-stu-id="409c4-105">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="409c4-106">Чтобы изменить дерево выражения, необходимо создать копию существующего дерева выражения, а затем внести необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="409c4-106">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="409c4-107">Для прохода по существующему дереву выражения и копирования каждого пройденного узла можно использовать класс <xref:System.Linq.Expressions.ExpressionVisitor>.</span><span class="sxs-lookup"><span data-stu-id="409c4-107">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="409c4-108">Изменение дерева выражения</span><span class="sxs-lookup"><span data-stu-id="409c4-108">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="409c4-109">Создайте новый проект **консольного приложения**.</span><span class="sxs-lookup"><span data-stu-id="409c4-109">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="409c4-110">Добавьте в файл директиву `using` для пространства имен `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="409c4-110">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="409c4-111">Добавьте в проект класс `AndAlsoModifier`.</span><span class="sxs-lookup"><span data-stu-id="409c4-111">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     <span data-ttu-id="409c4-112">Этот класс наследует класс <xref:System.Linq.Expressions.ExpressionVisitor> и специально предназначен для изменения выражений, которые представляют условные операции `AND`.</span><span class="sxs-lookup"><span data-stu-id="409c4-112">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="409c4-113">Он изменяет эти операции с условного `AND` на условное `OR`.</span><span class="sxs-lookup"><span data-stu-id="409c4-113">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="409c4-114">Для этого класс переопределяет метод <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> базового типа, потому что условные выражения `AND` представлены как двоичные выражения.</span><span class="sxs-lookup"><span data-stu-id="409c4-114">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="409c4-115">Если выражение, переданное в метод `VisitBinary`, представляет условную операцию `AND`, код создает новое выражение, которое содержит условный оператор `OR` вместо условного оператора `AND`.</span><span class="sxs-lookup"><span data-stu-id="409c4-115">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="409c4-116">Если выражение, передаваемое в `VisitBinary`, не представляет условную операцию `AND`, метод передает выполнение реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="409c4-116">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="409c4-117">Методы базового класса создают узлы, которые похожи на переданные деревья выражений, однако поддеревья этих деревьев заменены на деревья выражений, которые были рекурсивно созданы при обходе.</span><span class="sxs-lookup"><span data-stu-id="409c4-117">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="409c4-118">Добавьте в файл директиву `using` для пространства имен `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="409c4-118">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="409c4-119">Добавьте код в метод `Main` в файле Program.cs для создания дерева выражения и передачи его в метод, который изменит его.</span><span class="sxs-lookup"><span data-stu-id="409c4-119">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     <span data-ttu-id="409c4-120">В приведенном ниже коде создается выражение, которое содержит условную операцию `AND`.</span><span class="sxs-lookup"><span data-stu-id="409c4-120">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="409c4-121">Затем в нем создается экземпляр класса `AndAlsoModifier`, и в метод `Modify` этого класса передается выражение.</span><span class="sxs-lookup"><span data-stu-id="409c4-121">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="409c4-122">Как исходные, так и измененные деревья выражений выводятся для отображения изменения.</span><span class="sxs-lookup"><span data-stu-id="409c4-122">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="409c4-123">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="409c4-123">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="409c4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="409c4-124">See also</span></span>

- [<span data-ttu-id="409c4-125">Выполнение деревьев выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="409c4-125">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="409c4-126">Деревья выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="409c4-126">Expression Trees (C#)</span></span>](./index.md)
