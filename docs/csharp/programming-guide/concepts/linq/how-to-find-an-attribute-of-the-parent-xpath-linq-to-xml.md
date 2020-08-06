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
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)

Данный раздел показывает способ перехода к родительскому элементу и нахождения его атрибута.

Выражение XPath:

`../@id`

## <a name="example"></a>Пример

Сначала в данном примере осуществляется поиск элемента `Author`. Затем в нем осуществляется поиск атрибута `id` родительского элемента.

В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).

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

В этом примере выводятся следующие данные:

```output
Results are identical
id="bk101"
```
