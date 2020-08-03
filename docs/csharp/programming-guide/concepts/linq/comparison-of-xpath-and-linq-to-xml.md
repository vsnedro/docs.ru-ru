---
title: Сравнительные характеристики XPath и LINQ to XML
description: Узнайте о сходствах и различиях функциональных возможностей XPath и LINQ to XML в C#. Для запроса XML-дерева можно использовать и то и другое.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: e2f34903b20a53dea6e5ff4858d4fadaebd9c37a
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104005"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a><span data-ttu-id="771ae-104">Сравнительные характеристики XPath и LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="771ae-104">Comparison of XPath and LINQ to XML</span></span>
<span data-ttu-id="771ae-105">XPath и LINQ to XML имеют некоторые сходные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="771ae-105">XPath and LINQ to XML offer some similar functionality.</span></span> <span data-ttu-id="771ae-106">И то и другое можно использовать, чтобы запрашивать XML-дерево для возвращения таких результатов, как коллекция элементов, коллекция атрибутов, коллекция узлов или значение элемента или атрибута.</span><span class="sxs-lookup"><span data-stu-id="771ae-106">Both can be used to query an XML tree, returning such results as a collection of elements, a collection of attributes, a collection of nodes, or the value of an element or attribute.</span></span> <span data-ttu-id="771ae-107">Однако между ними также есть некоторые различия.</span><span class="sxs-lookup"><span data-stu-id="771ae-107">However, there are also some differences.</span></span>  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a><span data-ttu-id="771ae-108">Различия между XPath и LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="771ae-108">Differences Between XPath and LINQ to XML</span></span>  
 <span data-ttu-id="771ae-109">XPath не поддерживает проекции новых типов.</span><span class="sxs-lookup"><span data-stu-id="771ae-109">XPath does not allow projection of new types.</span></span> <span data-ttu-id="771ae-110">Может возвращать только коллекции узлов из дерева, тогда как LINQ to XML может выполнить запрос и спроецировать граф объектов или XML-дерево в новой форме.</span><span class="sxs-lookup"><span data-stu-id="771ae-110">It can only return collections of nodes from the tree, whereas LINQ to XML can execute a query and project an object graph or an XML tree in a new shape.</span></span> <span data-ttu-id="771ae-111">Запросы LINQ to XML гораздо более эффективны и обладают большим набором возможностей по сравнению с выражениями XPath.</span><span class="sxs-lookup"><span data-stu-id="771ae-111">LINQ to XML queries encompass much more functionality and are much more powerful than XPath expressions.</span></span>  
  
 <span data-ttu-id="771ae-112">Выражение XPath представлено в изолированном виде, внутри строки.</span><span class="sxs-lookup"><span data-stu-id="771ae-112">XPath expressions exist in isolation within a string.</span></span> <span data-ttu-id="771ae-113">Компилятор C# не может выполнить синтаксический анализ выражения XPath во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="771ae-113">The C# compiler cannot help parse the XPath expression at compile time.</span></span> <span data-ttu-id="771ae-114">Напротив, компилятор C# проводит синтаксический анализ и компилирует запросы LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="771ae-114">By contrast, LINQ to XML queries are parsed and compiled by the C# compiler.</span></span> <span data-ttu-id="771ae-115">Компилятор способен обнаруживать многие ошибки запроса.</span><span class="sxs-lookup"><span data-stu-id="771ae-115">The compiler is able to catch many query errors.</span></span>  
  
 <span data-ttu-id="771ae-116">Результаты XPath не являются строго типизированными.</span><span class="sxs-lookup"><span data-stu-id="771ae-116">XPath results are not strongly typed.</span></span> <span data-ttu-id="771ae-117">В некоторых ситуациях результатом вычисления выражения XPath является объект, а задача определения соответствующего типа и приведения результата в соответствии с необходимостью возлагается на разработчика.</span><span class="sxs-lookup"><span data-stu-id="771ae-117">In a number of circumstances, the result of evaluating an XPath expression is an object, and it is up to the developer to determine the proper type and cast the result as necessary.</span></span> <span data-ttu-id="771ae-118">В отличие от этого, проекции на основе запроса LINQ to XML являются строго типизированными.</span><span class="sxs-lookup"><span data-stu-id="771ae-118">By contrast, the projections from a LINQ to XML query are strongly typed.</span></span>  
  
## <a name="result-ordering"></a><span data-ttu-id="771ae-119">Упорядочение результатов</span><span class="sxs-lookup"><span data-stu-id="771ae-119">Result Ordering</span></span>  
 <span data-ttu-id="771ae-120">В документе XPath 1.0 Recommendation указано, что коллекция, которая является результатом вычисления выражения XPath, не упорядочена.</span><span class="sxs-lookup"><span data-stu-id="771ae-120">The XPath 1.0 Recommendation states that a collection that is the result of evaluating an XPath expression is unordered.</span></span>  
  
 <span data-ttu-id="771ae-121">Однако при просмотре коллекции, возвращенной методом оси XPath LINQ to XML, можно отметить, что узлы в коллекции возвращены в том же порядке, что и в документе.</span><span class="sxs-lookup"><span data-stu-id="771ae-121">However, when iterating through a collection returned by a LINQ to XML XPath axis method, the nodes in the collection are returned in document order.</span></span> <span data-ttu-id="771ae-122">И они располагаются так даже при доступе к осям XPath, где предикаты выражены в обратном порядке по отношению к документу, например `preceding` и `preceding-sibling`.</span><span class="sxs-lookup"><span data-stu-id="771ae-122">This is the case even when accessing the XPath axes where predicates are expressed in terms of reverse document order, such as `preceding` and `preceding-sibling`.</span></span>  
  
 <span data-ttu-id="771ae-123">В отличие от этого, большинство осей LINQ to XML возвращают коллекции в порядке, соответствующем документу, однако две из них, <xref:System.Xml.Linq.XNode.Ancestors%2A> и <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, возвращают коллекции в порядке, обратном по отношению к документу.</span><span class="sxs-lookup"><span data-stu-id="771ae-123">By contrast, most of the LINQ to XML axes return collections in document order, but two of them, <xref:System.Xml.Linq.XNode.Ancestors%2A> and <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, return collections in reverse document order.</span></span> <span data-ttu-id="771ae-124">В следующей таблице перечисляются эти оси и указывается порядок коллекций для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="771ae-124">The following table enumerates the axes, and indicates collection order for each:</span></span>  
  
|<span data-ttu-id="771ae-125">Ось LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="771ae-125">LINQ to XML axis</span></span>|<span data-ttu-id="771ae-126">Упорядочение</span><span class="sxs-lookup"><span data-stu-id="771ae-126">Ordering</span></span>|  
|----------------------|--------------|  
|<span data-ttu-id="771ae-127">XContainer.DescendantNodes</span><span class="sxs-lookup"><span data-stu-id="771ae-127">XContainer.DescendantNodes</span></span>|<span data-ttu-id="771ae-128">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-128">Document order</span></span>|  
|<span data-ttu-id="771ae-129">XContainer.Descendants</span><span class="sxs-lookup"><span data-stu-id="771ae-129">XContainer.Descendants</span></span>|<span data-ttu-id="771ae-130">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-130">Document order</span></span>|  
|<span data-ttu-id="771ae-131">XContainer.Elements</span><span class="sxs-lookup"><span data-stu-id="771ae-131">XContainer.Elements</span></span>|<span data-ttu-id="771ae-132">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-132">Document order</span></span>|  
|<span data-ttu-id="771ae-133">XContainer.Nodes</span><span class="sxs-lookup"><span data-stu-id="771ae-133">XContainer.Nodes</span></span>|<span data-ttu-id="771ae-134">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-134">Document order</span></span>|  
|<span data-ttu-id="771ae-135">XContainer.NodesAfterSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-135">XContainer.NodesAfterSelf</span></span>|<span data-ttu-id="771ae-136">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-136">Document order</span></span>|  
|<span data-ttu-id="771ae-137">XContainer.NodesBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-137">XContainer.NodesBeforeSelf</span></span>|<span data-ttu-id="771ae-138">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-138">Document order</span></span>|  
|<span data-ttu-id="771ae-139">XElement.AncestorsAndSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-139">XElement.AncestorsAndSelf</span></span>|<span data-ttu-id="771ae-140">Обратный порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-140">Reverse document order</span></span>|  
|<span data-ttu-id="771ae-141">XElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="771ae-141">XElement.Attributes</span></span>|<span data-ttu-id="771ae-142">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-142">Document order</span></span>|  
|<span data-ttu-id="771ae-143">XElement.DescendantNodesAndSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-143">XElement.DescendantNodesAndSelf</span></span>|<span data-ttu-id="771ae-144">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-144">Document order</span></span>|  
|<span data-ttu-id="771ae-145">XElement.DescendantsAndSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-145">XElement.DescendantsAndSelf</span></span>|<span data-ttu-id="771ae-146">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-146">Document order</span></span>|  
|<span data-ttu-id="771ae-147">XNode.Ancestors</span><span class="sxs-lookup"><span data-stu-id="771ae-147">XNode.Ancestors</span></span>|<span data-ttu-id="771ae-148">Обратный порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-148">Reverse document order</span></span>|  
|<span data-ttu-id="771ae-149">XNode.ElementsAfterSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-149">XNode.ElementsAfterSelf</span></span>|<span data-ttu-id="771ae-150">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-150">Document order</span></span>|  
|<span data-ttu-id="771ae-151">XNode.ElementsBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-151">XNode.ElementsBeforeSelf</span></span>|<span data-ttu-id="771ae-152">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-152">Document order</span></span>|  
|<span data-ttu-id="771ae-153">XNode.NodesAfterSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-153">XNode.NodesAfterSelf</span></span>|<span data-ttu-id="771ae-154">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-154">Document order</span></span>|  
|<span data-ttu-id="771ae-155">XNode.NodesBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="771ae-155">XNode.NodesBeforeSelf</span></span>|<span data-ttu-id="771ae-156">Порядок документа</span><span class="sxs-lookup"><span data-stu-id="771ae-156">Document order</span></span>|  
  
## <a name="positional-predicates"></a><span data-ttu-id="771ae-157">Позиционные предикаты</span><span class="sxs-lookup"><span data-stu-id="771ae-157">Positional Predicates</span></span>  
 <span data-ttu-id="771ae-158">В выражении XPath позиционные предикаты представляются с учетом порядка расположения в документе для многих осей, однако они располагаются в порядке, обратном по отношению к документу, для обратных осей, а именно `preceding`, `preceding-sibling`, `ancestor` и `ancestor-or-self`.</span><span class="sxs-lookup"><span data-stu-id="771ae-158">Within an XPath expression, positional predicates are expressed in terms of document order for many axes, but are expressed in reverse document order for reverse axes, which are `preceding`, `preceding-sibling`, `ancestor`, and `ancestor-or-self`.</span></span> <span data-ttu-id="771ae-159">Например, выражение XPath `preceding-sibling::*[1]` возвращает ближайший предшествующий одноуровневый элемент.</span><span class="sxs-lookup"><span data-stu-id="771ae-159">For example, the XPath expression `preceding-sibling::*[1]` returns the immediately preceding sibling.</span></span> <span data-ttu-id="771ae-160">Так происходит даже несмотря на то, что итоговый результирующий набор представляется в порядке документа.</span><span class="sxs-lookup"><span data-stu-id="771ae-160">This is the case even though the final result set is presented in document order.</span></span>  
  
 <span data-ttu-id="771ae-161">В отличие от этого все позиционные предикаты в LINQ to XML всегда выражаются в порядке оси.</span><span class="sxs-lookup"><span data-stu-id="771ae-161">By contrast, all positional predicates in LINQ to XML are always expressed in terms of the order of the axis.</span></span> <span data-ttu-id="771ae-162">Например, `anElement.ElementsBeforeSelf().ElementAt(0)` возвращает первый дочерний элемент родителя запрашиваемого элемента, а не ближайший предшествующий одноуровневый элемент.</span><span class="sxs-lookup"><span data-stu-id="771ae-162">For example, `anElement.ElementsBeforeSelf().ElementAt(0)` returns the first child element of the parent of the queried element, not the immediate preceding sibling.</span></span> <span data-ttu-id="771ae-163">Другой пример: `anElement.Ancestors().ElementAt(0)` возвращает родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="771ae-163">Another example: `anElement.Ancestors().ElementAt(0)` returns the parent element.</span></span>  
  
 <span data-ttu-id="771ae-164">Если вам необходимо найти ближайший предшествующий элемент в LINQ to XML, следует использовать выражение:</span><span class="sxs-lookup"><span data-stu-id="771ae-164">If you wanted to find the immediately preceding element in LINQ to XML, you would write the following expression:</span></span>  
  
```csharp
ElementsBeforeSelf().Last()
```
  
```vb
ElementsBeforeSelf().Last()
```
  
## <a name="performance-differences"></a><span data-ttu-id="771ae-165">Различия в производительности</span><span class="sxs-lookup"><span data-stu-id="771ae-165">Performance Differences</span></span>  
 <span data-ttu-id="771ae-166">Запросы XPath, которые используют функциональность XPath в LINQ to XML, менее производительны по сравнению с запросами LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="771ae-166">XPath queries that use the XPath functionality in LINQ to XML will not perform as well as LINQ to XML queries.</span></span>  
  
## <a name="comparison-of-composition"></a><span data-ttu-id="771ae-167">Сравнение композиций</span><span class="sxs-lookup"><span data-stu-id="771ae-167">Comparison of Composition</span></span>  
 <span data-ttu-id="771ae-168">Состав запроса LINQ to XML немного напоминает состав выражения XPath, хотя по синтаксису они совершенно различны.</span><span class="sxs-lookup"><span data-stu-id="771ae-168">Composition of a LINQ to XML query is somewhat parallel to composition of an XPath expression, although very different in syntax.</span></span>  
  
 <span data-ttu-id="771ae-169">Например, если в переменной с именем `customers` имеется элемент и требуется найти внучатый элемент с именем `CompanyName` во всех дочерних элементах с именем `Customer`, то нужно написать следующее выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="771ae-169">For example, if you have an element in a variable named `customers`, and you want to find a grandchild element named `CompanyName` under all child elements named `Customer`, you would write an XPath expression as follows:</span></span>  
  
```csharp  
customers.XPathSelectElements("./Customer/CompanyName")
```  
  
```vb
customers.XPathSelectElements("./Customer/CompanyName")
```

 <span data-ttu-id="771ae-170">Эквивалентный запрос LINQ to XML:</span><span class="sxs-lookup"><span data-stu-id="771ae-170">The equivalent LINQ to XML query is:</span></span>  
  
```csharp  
customers.Elements("Customer").Elements("CompanyName")
```  
  
```vb
customers.Elements("Customer").Elements("CompanyName")
```  

 <span data-ttu-id="771ae-171">Существуют похожие аналоги для каждой оси XPath.</span><span class="sxs-lookup"><span data-stu-id="771ae-171">There are similar parallels for each of the XPath axes.</span></span>  
  
|<span data-ttu-id="771ae-172">Ось XPath</span><span class="sxs-lookup"><span data-stu-id="771ae-172">XPath axis</span></span>|<span data-ttu-id="771ae-173">Ось LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="771ae-173">LINQ to XML axis</span></span>|  
|----------------|----------------------|  
|<span data-ttu-id="771ae-174">дочерняя (ось по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="771ae-174">child (the default axis)</span></span>|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-175">родительская (...)</span><span class="sxs-lookup"><span data-stu-id="771ae-175">Parent (..)</span></span>|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-176">ось атрибутов (@)</span><span class="sxs-lookup"><span data-stu-id="771ae-176">attribute axis (@)</span></span>|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="771ae-177">or</span><span class="sxs-lookup"><span data-stu-id="771ae-177">or</span></span><br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-178">ось ancestor</span><span class="sxs-lookup"><span data-stu-id="771ae-178">ancestor axis</span></span>|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-179">ось ancestor-or-self</span><span class="sxs-lookup"><span data-stu-id="771ae-179">ancestor-or-self axis</span></span>|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-180">дочерняя ось (//)</span><span class="sxs-lookup"><span data-stu-id="771ae-180">descendant axis (//)</span></span>|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="771ae-181">or</span><span class="sxs-lookup"><span data-stu-id="771ae-181">or</span></span><br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-182">descendant-or-self</span><span class="sxs-lookup"><span data-stu-id="771ae-182">descendant-or-self</span></span>|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="771ae-183">or</span><span class="sxs-lookup"><span data-stu-id="771ae-183">or</span></span><br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-184">following-sibling</span><span class="sxs-lookup"><span data-stu-id="771ae-184">following-sibling</span></span>|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="771ae-185">or</span><span class="sxs-lookup"><span data-stu-id="771ae-185">or</span></span><br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-186">preceding-sibling</span><span class="sxs-lookup"><span data-stu-id="771ae-186">preceding-sibling</span></span>|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="771ae-187">or</span><span class="sxs-lookup"><span data-stu-id="771ae-187">or</span></span><br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="771ae-188">following</span><span class="sxs-lookup"><span data-stu-id="771ae-188">following</span></span>|<span data-ttu-id="771ae-189">Непосредственного эквивалента нет.</span><span class="sxs-lookup"><span data-stu-id="771ae-189">No direct equivalent.</span></span>|  
|<span data-ttu-id="771ae-190">preceding</span><span class="sxs-lookup"><span data-stu-id="771ae-190">preceding</span></span>|<span data-ttu-id="771ae-191">Непосредственного эквивалента нет.</span><span class="sxs-lookup"><span data-stu-id="771ae-191">No direct equivalent.</span></span>|  
  