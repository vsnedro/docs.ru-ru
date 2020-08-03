---
title: Общие сведения о LINQ to XML (C#)
description: LINQ to XML использует платформу .NET LINQ Framework для предоставления возможностей изменения документов в памяти и выражений запросов с помощью таких функций, как XPath.
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: d2e4cf4e63d1a6ed7c1f0c163c12bb422b55ba11
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165351"
---
# <a name="linq-to-xml-overview-c"></a><span data-ttu-id="38a9a-103">Общие сведения о LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="38a9a-103">LINQ to XML Overview (C#)</span></span>

<span data-ttu-id="38a9a-104">LINQ to XML обеспечивает интерфейс программирования для работы с XML в памяти на основе платформы .NET LINQ Framework.</span><span class="sxs-lookup"><span data-stu-id="38a9a-104">LINQ to XML provides an in-memory XML programming interface that leverages the .NET Language-Integrated Query (LINQ) Framework.</span></span> <span data-ttu-id="38a9a-105">Интерфейс LINQ to XML использует возможности .NET и может быть сравним с обновленным, переработанным программным интерфейсом XML модели DOM.</span><span class="sxs-lookup"><span data-stu-id="38a9a-105">LINQ to XML uses .NET capabilities and is comparable to an updated, redesigned Document Object Model (DOM) XML programming interface.</span></span>

<span data-ttu-id="38a9a-106">XML широко используется для форматирования данных в целом ряде контекстов.</span><span class="sxs-lookup"><span data-stu-id="38a9a-106">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="38a9a-107">Примеры XML можно обнаружить в веб-среде, в файлах конфигурации, в файлах Microsoft Office Word и в базах данных.</span><span class="sxs-lookup"><span data-stu-id="38a9a-107">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>

<span data-ttu-id="38a9a-108">В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] реализован современный пересмотренный подход к программированию средствами XML.</span><span class="sxs-lookup"><span data-stu-id="38a9a-108">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="38a9a-109">Он позволяет изменять документы в оперативной памяти на основе модели DOM и поддерживает выражения запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="38a9a-109">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports LINQ query expressions.</span></span> <span data-ttu-id="38a9a-110">Хотя в синтаксическом отношении эти выражения запросов отличаются от XPath, они предоставляют аналогичные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="38a9a-110">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>

## <a name="linq-to-xml-developers"></a><span data-ttu-id="38a9a-111">Разработчики, использующие LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="38a9a-111">LINQ to XML Developers</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="38a9a-112">предназначен для различных категорий разработчиков.</span><span class="sxs-lookup"><span data-stu-id="38a9a-112">targets a variety of developers.</span></span> <span data-ttu-id="38a9a-113">С точки зрения среднестатистического разработчика, заинтересованного в решении той или иной задачи, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] облегчает обработку XML, поскольку дает возможность получить опыт работы с запросами, аналогичный опыту работы с языком SQL.</span><span class="sxs-lookup"><span data-stu-id="38a9a-113">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="38a9a-114">Посвятив совсем немного времени изучению предмета, программисты могут научиться составлять сжатые и мощные запросы на предпочитаемом ими языке программирования.</span><span class="sxs-lookup"><span data-stu-id="38a9a-114">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>

<span data-ttu-id="38a9a-115">Профессиональные разработчики могут с помощью [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] существенно повысить производительность своего труда.</span><span class="sxs-lookup"><span data-stu-id="38a9a-115">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="38a9a-116">Используя [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], они могут сократить объемы необходимого кода и сделать его более выразительным, более компактным и более мощным.</span><span class="sxs-lookup"><span data-stu-id="38a9a-116">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="38a9a-117">Они могут одновременно использовать выражения запросов из нескольких доменов данных.</span><span class="sxs-lookup"><span data-stu-id="38a9a-117">They can use query expressions from multiple data domains at the same time.</span></span>

## <a name="what-is-linq-to-xml"></a><span data-ttu-id="38a9a-118">Что такое LINQ to XML?</span><span class="sxs-lookup"><span data-stu-id="38a9a-118">What Is LINQ to XML?</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="38a9a-119">— это оснащенный средствами LINQ и встроенный в память программный интерфейс XML, позволяющий работать с XML-файлами изнутри языков программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="38a9a-119">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET programming languages.</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="38a9a-120">подобен модели DOM в том отношении, что загружает XML-документ в память.</span><span class="sxs-lookup"><span data-stu-id="38a9a-120">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="38a9a-121">К такому документу можно направить запрос, его можно изменить, а после изменения его можно сохранить в файле или сериализовать и передать через Интернет.</span><span class="sxs-lookup"><span data-stu-id="38a9a-121">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="38a9a-122">Но между [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] и моделью DOM существуют отличия: Интерфейс реализует облегченную и более простую в работе модель объектов; кроме того, в нем используются преимущества языковых возможностей, реализованные в C#.</span><span class="sxs-lookup"><span data-stu-id="38a9a-122">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in C#.</span></span>

<span data-ttu-id="38a9a-123">Важнейшее достоинство [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] представлено интеграцией с LINQ.</span><span class="sxs-lookup"><span data-stu-id="38a9a-123">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="38a9a-124">Эта интеграция дает возможность создавать запросы к загруженному в память XML-документу с целью получения коллекций элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="38a9a-124">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="38a9a-125">По своей функциональности (но не по синтаксису) реализованные в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] возможности формирования запросов сопоставимы с возможностями XPath и XQuery.</span><span class="sxs-lookup"><span data-stu-id="38a9a-125">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="38a9a-126">Интеграция LINQ в C# обеспечивает более строгую типизацию, проверку во время компиляции и улучшенную поддержку отладчика.</span><span class="sxs-lookup"><span data-stu-id="38a9a-126">The integration of LINQ in C# provides stronger typing, compile-time checking, and improved debugger support.</span></span>

<span data-ttu-id="38a9a-127">Другим преимуществом [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] является то, что возможность использования результатов запросов в качестве параметров конструкторов объектов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XAttribute> позволяет применять мощный подход для создания XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="38a9a-127">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="38a9a-128">Этот подход, известный как *функциональное построение*, дает разработчикам возможность легко преобразовывать деревья XML из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="38a9a-128">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>

<span data-ttu-id="38a9a-129">Пусть имеется типичный заказ на покупку в формате XML, как это описано в статье [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="38a9a-129">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span> <span data-ttu-id="38a9a-130">С помощью интерфейса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно выполнить следующий запрос для получения значения атрибута артикула для каждого элемента в заказе на покупку:</span><span class="sxs-lookup"><span data-stu-id="38a9a-130">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

<span data-ttu-id="38a9a-131">Это можно переписать в форме синтаксиса метода:</span><span class="sxs-lookup"><span data-stu-id="38a9a-131">This can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

<span data-ttu-id="38a9a-132">Еще один пример. Пусть требуется сформировать отсортированный в соответствии с номерами деталей список продуктов стоимостью выше 100 долл.</span><span class="sxs-lookup"><span data-stu-id="38a9a-132">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="38a9a-133">Для получения этих сведений можно выполнить следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="38a9a-133">To obtain this information, you could run the following query:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

<span data-ttu-id="38a9a-134">Опять же, это можно переписать в форме синтаксиса метода:</span><span class="sxs-lookup"><span data-stu-id="38a9a-134">Again, this can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

<span data-ttu-id="38a9a-135">В дополнение к функциям, реализованным в LINQ, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предоставляет усовершенствованный интерфейс программирования XML.</span><span class="sxs-lookup"><span data-stu-id="38a9a-135">In addition to these LINQ capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="38a9a-136">Благодаря [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] появляются следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="38a9a-136">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>

- <span data-ttu-id="38a9a-137">Загрузка XML из [файлов](how-to-load-xml-from-a-file.md) или из [потоков](how-to-stream-xml-fragments-from-an-xmlreader.md).</span><span class="sxs-lookup"><span data-stu-id="38a9a-137">Load XML from [files](how-to-load-xml-from-a-file.md) or [streams](how-to-stream-xml-fragments-from-an-xmlreader.md).</span></span>

- <span data-ttu-id="38a9a-138">Сериализация XML в файлы или в потоки.</span><span class="sxs-lookup"><span data-stu-id="38a9a-138">Serialize XML to files or streams.</span></span>

- <span data-ttu-id="38a9a-139">Создание XML-кодов «с чистого листа» с помощью функционального построения.</span><span class="sxs-lookup"><span data-stu-id="38a9a-139">Create XML from scratch by using functional construction.</span></span>

- <span data-ttu-id="38a9a-140">Обращение с запросами к XML с помощью XPath-подобных осей.</span><span class="sxs-lookup"><span data-stu-id="38a9a-140">Query XML using XPath-like axes.</span></span>

- <span data-ttu-id="38a9a-141">Манипулирование загруженным в память XML-деревом с помощью таких методов, как <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> и <xref:System.Xml.Linq.XElement.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="38a9a-141">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>

- <span data-ttu-id="38a9a-142">Проверка XML-деревьев с помощью XSD.</span><span class="sxs-lookup"><span data-stu-id="38a9a-142">Validate XML trees using XSD.</span></span>

- <span data-ttu-id="38a9a-143">Использование сочетания этих функций для преобразования XML-деревьев из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="38a9a-143">Use a combination of these features to transform XML trees from one shape into another.</span></span>

## <a name="creating-xml-trees"></a><span data-ttu-id="38a9a-144">Создание деревьев XML</span><span class="sxs-lookup"><span data-stu-id="38a9a-144">Creating XML Trees</span></span>

<span data-ttu-id="38a9a-145">Одним из наиболее важных преимуществ программирования с использованием [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] является простота создания XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="38a9a-145">One of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="38a9a-146">Так, для создания небольшого дерева XML можно написать следующий код:</span><span class="sxs-lookup"><span data-stu-id="38a9a-146">For example, to create a small XML tree, you can write code as follows:</span></span>

```csharp
XElement contacts =
new XElement("Contacts",
    new XElement("Contact",
        new XElement("Name", "Patrick Hines"),
        new XElement("Phone", "206-555-0144",
            new XAttribute("Type", "Home")),
        new XElement("phone", "425-555-0145",
            new XAttribute("Type", "Work")),
        new XElement("Address",
            new XElement("Street1", "123 Main St"),
            new XElement("City", "Mercer Island"),
            new XElement("State", "WA"),
            new XElement("Postal", "68042")
        )
    )
);
```

<span data-ttu-id="38a9a-147">Дополнительные сведения см. в разделе [Создание деревьев XML (C#)](./creating-xml-trees-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="38a9a-147">For more information, see [Creating XML Trees (C#)](./creating-xml-trees-linq-to-xml-2.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38a9a-148">См. также</span><span class="sxs-lookup"><span data-stu-id="38a9a-148">See also</span></span>

- [<span data-ttu-id="38a9a-149">Ссылка (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="38a9a-149">Reference (LINQ to XML)</span></span>](./reference-linq-to-xml.md)
- [<span data-ttu-id="38a9a-150">Сравнение LINQ to XML с моделью DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="38a9a-150">LINQ to XML vs. DOM (C#)</span></span>](./linq-to-xml-vs-dom.md)
- [<span data-ttu-id="38a9a-151">Сравнение LINQ to XML с другими XML-технологиями</span><span class="sxs-lookup"><span data-stu-id="38a9a-151">LINQ to XML vs. Other XML Technologies</span></span>](./linq-to-xml-vs-other-xml-technologies.md)
- <xref:System.Xml.Linq>
