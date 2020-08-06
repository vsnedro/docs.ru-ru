---
title: Сортировка элементов (C#)
description: Сведения о сортировке элементов. Ознакомьтесь с примерами составления запросов для сортировки результатов в XML-документе.
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 669d9cf583e6ab70c93be39ad271eaf104f88718
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301441"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="6c9ed-104">Сортировка элементов (C#)</span><span class="sxs-lookup"><span data-stu-id="6c9ed-104">How to sort elements (C#)</span></span>
<span data-ttu-id="6c9ed-105">В этом примере показано, как создавать запросы с сортировкой результатов.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-105">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c9ed-106">Пример</span><span class="sxs-lookup"><span data-stu-id="6c9ed-106">Example</span></span>  
 <span data-ttu-id="6c9ed-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6c9ed-107">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> prices =  
    from el in root.Elements("Data")  
    let price = (decimal)el.Element("Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="6c9ed-108">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="6c9ed-108">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="6c9ed-109">Пример</span><span class="sxs-lookup"><span data-stu-id="6c9ed-109">Example</span></span>  
 <span data-ttu-id="6c9ed-110">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="6c9ed-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="6c9ed-111">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6c9ed-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="6c9ed-112">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные в пространстве имен](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="6c9ed-112">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace aw = "http://www.adatum.com";  
IEnumerable<decimal> prices =  
    from el in root.Elements(aw + "Data")  
    let price = (decimal)el.Element(aw + "Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="6c9ed-113">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="6c9ed-113">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c9ed-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6c9ed-114">See also</span></span>

- [<span data-ttu-id="6c9ed-115">Сортировка данных (C#)</span><span class="sxs-lookup"><span data-stu-id="6c9ed-115">Sorting Data (C#)</span></span>](./sorting-data.md)
