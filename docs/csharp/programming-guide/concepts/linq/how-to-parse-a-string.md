---
title: Анализ строки (C#)
description: Узнайте, как в C# анализировать строку для создания XML-дерева. Узнайте, как получить доступ к определенным данным в проанализированном XML.
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: a4664e090b6a44c52c519e61b66ccdc5d59a71f1
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104807"
---
# <a name="how-to-parse-a-string-c"></a>Анализ строки (C#)

В этом разделе демонстрируется анализ строки для создания XML-дерева в C#.

## <a name="example"></a>Пример

В следующем коде C# показано, как выполнять синтаксический анализ строки XML.

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

Корневой узел `Contacts` содержит два узла `Contact`. Для доступа к определенным данным в проанализированном XML используйте метод [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements), который в этом случае возвращает дочерние элементы корневого узла `Contacts`. В следующем примере в окне консоли выводится первый узел `Contact`:

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a>См. также

- [Практическое руководство. Поиск элементов с определенным атрибутом (C#)](how-to-find-an-element-with-a-specific-attribute.md)
