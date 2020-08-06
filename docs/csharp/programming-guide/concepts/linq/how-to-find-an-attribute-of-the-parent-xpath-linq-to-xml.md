---
title: Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)
description: Узнайте, как найти атрибут родительского элемента. Ознакомьтесь с примером кода, в котором используется XML-документ.
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 03344bb66f617970d9598c91366eb7d69514397a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303300"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="2831c-104">Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2831c-104">How to find an attribute of the parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="2831c-105">Данный раздел показывает способ перехода к родительскому элементу и нахождения его атрибута.</span><span class="sxs-lookup"><span data-stu-id="2831c-105">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="2831c-106">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="2831c-106">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="2831c-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2831c-107">Example</span></span>

<span data-ttu-id="2831c-108">Сначала в данном примере осуществляется поиск элемента `Author`.</span><span class="sxs-lookup"><span data-stu-id="2831c-108">This example first finds an `Author` element.</span></span> <span data-ttu-id="2831c-109">Затем в нем осуществляется поиск атрибута `id` родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="2831c-109">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="2831c-110">В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2831c-110">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

<span data-ttu-id="2831c-111">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="2831c-111">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```
