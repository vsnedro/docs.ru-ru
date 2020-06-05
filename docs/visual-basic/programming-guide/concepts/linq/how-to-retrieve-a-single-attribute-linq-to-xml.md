---
title: Практическое руководство. Извлечение одного атрибута (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 11b938d7-c011-4048-900e-8b9183c41c94
ms.openlocfilehash: 34c390fbffc1aea68a2fd8ae64b17d2637a1f4f1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397860"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="24557-102">Как получить один атрибут (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24557-102">How to: Retrieve a Single Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="24557-103">В этом разделе приведены объяснения способа получения одного атрибута элемента при условии, что название атрибута известно.</span><span class="sxs-lookup"><span data-stu-id="24557-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="24557-104">Это полезно для составления выражений запросов, при которых требуется найти элемент с определенным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="24557-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="24557-105">Метод <xref:System.Xml.Linq.XElement.Attribute%2A> класса <xref:System.Xml.Linq.XElement> возвращает значение <xref:System.Xml.Linq.XAttribute> с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="24557-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24557-106">Пример</span><span class="sxs-lookup"><span data-stu-id="24557-106">Example</span></span>  
 <span data-ttu-id="24557-107">В следующем примере используется метод <xref:System.Xml.Linq.XElement.Attribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="24557-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList = From el In cust...<Phone>  
For Each e As XElement In elList  
    Console.WriteLine(e.@type)  
Next  
```  
  
 <span data-ttu-id="24557-108">В этом примере выполняется поиск всех потомков в дереве с названием `Phone`, затем атрибута с названием `type`.</span><span class="sxs-lookup"><span data-stu-id="24557-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="24557-109">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="24557-109">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="24557-110">Пример</span><span class="sxs-lookup"><span data-stu-id="24557-110">Example</span></span>  
 <span data-ttu-id="24557-111">Если требуется получить значение атрибута, можно его задать точно так же, как при работе с объектами <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="24557-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="24557-112">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="24557-112">The following example demonstrates this.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList As IEnumerable(Of XElement) = _  
    From el In cust...<Phone> _  
    Select el  
For Each el As XElement In elList  
    Console.WriteLine(el.@type)  
Next  
```  
  
 <span data-ttu-id="24557-113">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="24557-113">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="24557-114">предоставляет явные операторы приведения класса <xref:System.Xml.Linq.XAttribute> к `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` и `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="24557-114">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24557-115">Пример</span><span class="sxs-lookup"><span data-stu-id="24557-115">Example</span></span>  
 <span data-ttu-id="24557-116">Следующий пример демонстрирует тот же код атрибута, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="24557-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="24557-117">Дополнительные сведения см. в разделе [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="24557-117">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cust As XElement = _  
            <aw:PhoneNumbers>  
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>  
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>  
            </aw:PhoneNumbers>  
        Dim elList As IEnumerable(Of XElement) = _  
            From el In cust...<aw:Phone> _  
            Select el  
        For Each el As XElement In elList  
            Console.WriteLine(el.@aw:type)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="24557-118">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="24557-118">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="24557-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="24557-119">See also</span></span>

- [<span data-ttu-id="24557-120">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24557-120">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
