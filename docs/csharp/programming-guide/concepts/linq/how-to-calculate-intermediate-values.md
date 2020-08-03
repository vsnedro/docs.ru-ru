---
title: Практическое руководство. Вычисление промежуточных значений (C#)
description: В этом примере LINQ to XML в C# показано, как вычислять промежуточные значения, которые используются в сортировке, фильтрации и выборке.
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: fc648f20550de13735a1f6da6b2f811fd0d39004
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103614"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="38194-103">Практическое руководство. Вычисление промежуточных значений (C#)</span><span class="sxs-lookup"><span data-stu-id="38194-103">How to calculate intermediate values (C#)</span></span>
<span data-ttu-id="38194-104">В этом примере показано, как вычислять промежуточные значения, которые используются в сортировке, фильтрации и выборке.</span><span class="sxs-lookup"><span data-stu-id="38194-104">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38194-105">Пример</span><span class="sxs-lookup"><span data-stu-id="38194-105">Example</span></span>  
 <span data-ttu-id="38194-106">В следующем примере используется предложение `Let`.</span><span class="sxs-lookup"><span data-stu-id="38194-106">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="38194-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="38194-107">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="38194-108">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="38194-108">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="38194-109">Пример</span><span class="sxs-lookup"><span data-stu-id="38194-109">Example</span></span>  
 <span data-ttu-id="38194-110">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="38194-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="38194-111">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="38194-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="38194-112">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные в пространстве имен](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="38194-112">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="38194-113">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="38194-113">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
