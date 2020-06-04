---
title: Практическое руководство. Извлечение поверхностного значения элемента
ms.date: 07/20/2015
ms.assetid: 730a6670-fb8c-41fc-8a1b-eb97a837e432
ms.openlocfilehash: 24e6b128481f56941f0a61da9766f02813a46e97
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397821"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-visual-basic"></a><span data-ttu-id="22381-102">Как извлечь неглубокое значение элемента (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22381-102">How to: Retrieve the Shallow Value of an Element (Visual Basic)</span></span>

<span data-ttu-id="22381-103">В этом разделе показано, как получить неглубокое значение элемента.</span><span class="sxs-lookup"><span data-stu-id="22381-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="22381-104">Неглубокое значение - это значение только конкретного элемента, в отличие от глубокого значения, которое содержит значения всех элементов-потомков, объединенные в одной строке.</span><span class="sxs-lookup"><span data-stu-id="22381-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>

<span data-ttu-id="22381-105">При получении значения элемента при помощи приведения или свойства <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> выполняется извлечение глубокого значения.</span><span class="sxs-lookup"><span data-stu-id="22381-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="22381-106">Чтобы получить неглубокое значение, можно использовать метод расширения `ShallowValue`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="22381-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the following example.</span></span> <span data-ttu-id="22381-107">Извлечение неглубокого значения полезно тогда, когда требуется выбрать элементы в зависимости от их содержимого.</span><span class="sxs-lookup"><span data-stu-id="22381-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>

<span data-ttu-id="22381-108">В следующем примере объявляется метод расширений, который извлекает неглубокое значение элемента.</span><span class="sxs-lookup"><span data-stu-id="22381-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="22381-109">После этого метод расширения используется в запросе, чтобы вывести список всех элементов с вычисленным значением.</span><span class="sxs-lookup"><span data-stu-id="22381-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>

## <a name="example"></a><span data-ttu-id="22381-110">Пример</span><span class="sxs-lookup"><span data-stu-id="22381-110">Example</span></span>

<span data-ttu-id="22381-111">Следующий текстовый файл Report.xml в этом примере будет исходным.</span><span class="sxs-lookup"><span data-stu-id="22381-111">The following text file, Report.xml, is the source for this example.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Report>
  <Section>
    <Heading>
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>
      <Column Name="Name">=Customer.Name.Heading</Column>
    </Heading>
    <Detail>
      <Column Name="CustomerId">=Customer.CustomerId</Column>
      <Column Name="Name">=Customer.Name</Column>
    </Detail>
  </Section>
</Report>
```

```vb
Module Module1
    <System.Runtime.CompilerServices.Extension()> _
    Public Function ShallowValue(ByVal xe As XElement)
        Return xe _
               .Nodes() _
               .OfType(Of XText)() _
               .Aggregate(New StringBuilder(), _
                              Function(s, c) s.Append(c), _
                              Function(s) s.ToString())
    End Function

    Sub Main()
        Dim root As XElement = XElement.Load("Report.xml")

        Dim query As IEnumerable(Of XElement) = _
            From el In root.Descendants() _
            Where (el.ShallowValue().StartsWith("=")) _
            Select el

        For Each q As XElement In query
            Console.WriteLine("{0}{1}{2}", _
                q.Name.ToString().PadRight(8), _
                q.Attribute("Name").ToString().PadRight(20), _
                q.ShallowValue())
        Next
    End Sub
End Module
```

<span data-ttu-id="22381-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="22381-112">This example produces the following output:</span></span>

```console
Column  Name="CustomerId"   =Customer.CustomerId.Heading
Column  Name="Name"         =Customer.Name.Heading
Column  Name="CustomerId"   =Customer.CustomerId
Column  Name="Name"         =Customer.Name
```

## <a name="see-also"></a><span data-ttu-id="22381-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="22381-113">See also</span></span>

- [<span data-ttu-id="22381-114">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22381-114">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
