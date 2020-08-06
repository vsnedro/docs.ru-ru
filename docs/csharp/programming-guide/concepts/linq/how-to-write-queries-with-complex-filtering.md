---
title: Создание запросов со сложной фильтрацией (C#)
description: Сведения о написании запросов LINQ to XML с комплексной фильтрацией. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 5d2c1aafc210b35d4d6b1f1b2d74b11966d90c80
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303430"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="cae68-104">Создание запросов со сложной фильтрацией (C#)</span><span class="sxs-lookup"><span data-stu-id="cae68-104">How to write queries with complex filtering (C#)</span></span>
<span data-ttu-id="cae68-105">Иногда возникает необходимость в написании запросов LINQ to XML с комплексной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="cae68-105">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="cae68-106">Например, может потребоваться найти все элементы, имеющие дочерние элементы с определенным именем и значением.</span><span class="sxs-lookup"><span data-stu-id="cae68-106">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="cae68-107">В этом разделе приводится пример написания запроса с комплексной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="cae68-107">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cae68-108">Пример</span><span class="sxs-lookup"><span data-stu-id="cae68-108">Example</span></span>  
 <span data-ttu-id="cae68-109">В этом примере показано, как найти все элементы `PurchaseOrder`, имеющие дочерний элемент `Address` с атрибутом `Type`, равным «Доставка», и дочерним элементом `State`, равным «NY».</span><span class="sxs-lookup"><span data-stu-id="cae68-109">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="cae68-110">В нем используется вложенный запрос в предложении `Where`, а оператор `Any` возвращает значение `true`, если коллекция содержит элементы.</span><span class="sxs-lookup"><span data-stu-id="cae68-110">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="cae68-111">Сведения об использовании синтаксиса запросов на основе методов см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](./query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="cae68-111">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="cae68-112">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cae68-112">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="cae68-113">Дополнительные сведения об операторе `Any` см. в разделе [Операции, использующие квантификаторы (C#)](./quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="cae68-113">For more information about the `Any` operator, see [Quantifier Operations (C#)](./quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="cae68-114">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="cae68-114">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="cae68-115">Пример</span><span class="sxs-lookup"><span data-stu-id="cae68-115">Example</span></span>  
 <span data-ttu-id="cae68-116">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="cae68-116">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="cae68-117">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cae68-117">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="cae68-118">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку в пространстве имен](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="cae68-118">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="cae68-119">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="cae68-119">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="cae68-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cae68-120">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="cae68-121">Операции проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="cae68-121">Projection Operations (C#)</span></span>](./projection-operations.md)
- [<span data-ttu-id="cae68-122">Операции, использующие квантификаторы (C#)</span><span class="sxs-lookup"><span data-stu-id="cae68-122">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)
