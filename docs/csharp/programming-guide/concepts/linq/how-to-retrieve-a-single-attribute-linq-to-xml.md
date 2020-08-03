---
title: Извлечение одного атрибута (LINQ to XML) (C#)
description: Узнайте, как использовать LINQ to XML для получения одного атрибута элемента C# при условии, что известно имя атрибута.
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: 4efcae5324ad5a2e4664e68e35e15ec2053daece
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103429"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a><span data-ttu-id="43e06-103">Извлечение одного атрибута (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="43e06-103">How to retrieve a single attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="43e06-104">В этом разделе приведены объяснения способа получения одного атрибута элемента при условии, что название атрибута известно.</span><span class="sxs-lookup"><span data-stu-id="43e06-104">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="43e06-105">Это полезно для составления выражений запросов, при которых требуется найти элемент с определенным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="43e06-105">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="43e06-106">Метод <xref:System.Xml.Linq.XElement.Attribute%2A> класса <xref:System.Xml.Linq.XElement> возвращает значение <xref:System.Xml.Linq.XAttribute> с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="43e06-106">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43e06-107">Пример</span><span class="sxs-lookup"><span data-stu-id="43e06-107">Example</span></span>  
 <span data-ttu-id="43e06-108">В следующем примере используется метод <xref:System.Xml.Linq.XElement.Attribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="43e06-108">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="43e06-109">В этом примере выполняется поиск всех потомков в дереве с названием `Phone`, затем атрибута с названием `type`.</span><span class="sxs-lookup"><span data-stu-id="43e06-109">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="43e06-110">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="43e06-110">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="43e06-111">Пример</span><span class="sxs-lookup"><span data-stu-id="43e06-111">Example</span></span>  
 <span data-ttu-id="43e06-112">Если требуется получить значение атрибута, можно его задать точно так же, как при работе с объектами <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="43e06-112">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="43e06-113">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="43e06-113">The following example demonstrates this.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="43e06-114">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="43e06-114">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="43e06-115">предоставляет явные операторы приведения класса <xref:System.Xml.Linq.XAttribute> к `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` и `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="43e06-115">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43e06-116">Пример</span><span class="sxs-lookup"><span data-stu-id="43e06-116">Example</span></span>  
 <span data-ttu-id="43e06-117">Следующий пример демонстрирует тот же код атрибута, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="43e06-117">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="43e06-118">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="43e06-118">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 <span data-ttu-id="43e06-119">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="43e06-119">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="43e06-120">См. также</span><span class="sxs-lookup"><span data-stu-id="43e06-120">See also</span></span>

- [<span data-ttu-id="43e06-121">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="43e06-121">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
