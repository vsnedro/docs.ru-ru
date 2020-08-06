---
title: Практическое руководство. Поиск одного потомка с помощью метода потомков (C#)
description: Узнайте, как найти одного потомка с помощью метода оси Descendants. Этот метод полезен при поиске конкретного потомка с определенным именем.
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: 993e2b45f93509cf526d0c8c5de488b50de3efef
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303339"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a><span data-ttu-id="76fdb-104">Практическое руководство. Поиск одного потомка с помощью метода потомков (C#)</span><span class="sxs-lookup"><span data-stu-id="76fdb-104">How to find a single descendant using the descendants method (C#)</span></span>
<span data-ttu-id="76fdb-105">Метод оси <xref:System.Xml.Linq.XContainer.Descendants%2A> можно использовать для быстрого написания кода с целью поиска одного уникально именованного элемента.</span><span class="sxs-lookup"><span data-stu-id="76fdb-105">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="76fdb-106">Этот способ особенно полезен, если нужно найти конкретного потомка с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="76fdb-106">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="76fdb-107">Можно написать собственный код для перехода к нужному элементу, но часто быстрей и легче написать такой код с помощью оси <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="76fdb-107">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76fdb-108">Пример</span><span class="sxs-lookup"><span data-stu-id="76fdb-108">Example</span></span>  
 <span data-ttu-id="76fdb-109">В этом примере используется стандартный оператор запроса <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="76fdb-109">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="76fdb-110">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="76fdb-110">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="76fdb-111">Пример</span><span class="sxs-lookup"><span data-stu-id="76fdb-111">Example</span></span>  
 <span data-ttu-id="76fdb-112">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="76fdb-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="76fdb-113">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="76fdb-113">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="76fdb-114">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="76fdb-114">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
