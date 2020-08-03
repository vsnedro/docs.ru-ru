---
title: Практическое руководство. Создание документа с пространствами имен (C#) (LINQ to XML)
description: Узнайте, как в LINQ to XML в C# создать документ с пространством имен с помощью объекта XNamespace, чтобы объединить пространство имен с локальным именем.
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 6472baefc73285af1c6dca0bfe7d874003940fc4
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103398"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a><span data-ttu-id="00fef-103">Практическое руководство. Создание документа с пространствами имен (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="00fef-103">How to create a document with namespaces (C#) (LINQ to XML)</span></span>
<span data-ttu-id="00fef-104">В этом разделе описано, как создавать документы с пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="00fef-104">This topic shows how to create documents with namespaces.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00fef-105">Пример</span><span class="sxs-lookup"><span data-stu-id="00fef-105">Example</span></span>  
 <span data-ttu-id="00fef-106">Чтобы создать элемент или атрибут, находящийся в пространстве имен, необходимо сначала объявить и инициализировать объект <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="00fef-106">To create an element or an attribute that is in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="00fef-107">Затем следует использовать перегруженный оператор сложения для объединения пространства имен с локальным именем, выраженным строкой.</span><span class="sxs-lookup"><span data-stu-id="00fef-107">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>  
  
 <span data-ttu-id="00fef-108">В следующем примере создается документ с одним пространством имен.</span><span class="sxs-lookup"><span data-stu-id="00fef-108">The following example creates a document with one namespace.</span></span> <span data-ttu-id="00fef-109">По умолчанию [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] сериализует документ с использованием пространства имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00fef-109">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializes this document with a default namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="00fef-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="00fef-110">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="00fef-111">Пример</span><span class="sxs-lookup"><span data-stu-id="00fef-111">Example</span></span>  
 <span data-ttu-id="00fef-112">В следующем примере создается документ с одним пространством имен.</span><span class="sxs-lookup"><span data-stu-id="00fef-112">The following example creates a document with one namespace.</span></span> <span data-ttu-id="00fef-113">Он также создает атрибут, который объявляет пространство имен с префиксом пространства имен.</span><span class="sxs-lookup"><span data-stu-id="00fef-113">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="00fef-114">Создать атрибут, объявляющий пространство имен с префиксом, можно, указав имя атрибута в качестве префикса пространства имен и поместив его в пространство имен <xref:System.Xml.Linq.XNamespace.Xmlns%2A>.</span><span class="sxs-lookup"><span data-stu-id="00fef-114">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="00fef-115">Значение этого атрибута представляет собой URI пространства имен.</span><span class="sxs-lookup"><span data-stu-id="00fef-115">The value of this attribute is the URI of the namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="00fef-116">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="00fef-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="00fef-117">Пример</span><span class="sxs-lookup"><span data-stu-id="00fef-117">Example</span></span>  
 <span data-ttu-id="00fef-118">Следующий пример иллюстрирует создание документа, содержащего два пространства имен.</span><span class="sxs-lookup"><span data-stu-id="00fef-118">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="00fef-119">Одно из них - пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00fef-119">One is the default namespace.</span></span> <span data-ttu-id="00fef-120">Другое - пространство имен с префиксом.</span><span class="sxs-lookup"><span data-stu-id="00fef-120">Another is a namespace with a prefix.</span></span>  
  
 <span data-ttu-id="00fef-121">При включении атрибутов пространств имен в корневой элемент пространства имен сериализуются, поэтому `http://www.adventure-works.com` становится пространством имен по умолчанию, а `www.fourthcoffee.com` сериализуется с префиксом "fc".</span><span class="sxs-lookup"><span data-stu-id="00fef-121">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of "fc".</span></span> <span data-ttu-id="00fef-122">Чтобы создать атрибут, объявляющий применяемое по умолчанию пространство имен, необходимо создать атрибут с именем «xmlns» без пространства имен.</span><span class="sxs-lookup"><span data-stu-id="00fef-122">To create an attribute that declares a default namespace, you create an attribute with the name "xmlns", without a namespace.</span></span> <span data-ttu-id="00fef-123">Значение этого атрибута является используемым по умолчанию идентификатором URI пространства имен.</span><span class="sxs-lookup"><span data-stu-id="00fef-123">The value of the attribute is the default namespace URI.</span></span>  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="00fef-124">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="00fef-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="00fef-125">Пример</span><span class="sxs-lookup"><span data-stu-id="00fef-125">Example</span></span>  
 <span data-ttu-id="00fef-126">В этом примере создается документ, который содержит два пространства имен с префиксами.</span><span class="sxs-lookup"><span data-stu-id="00fef-126">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="00fef-127">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="00fef-127">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="00fef-128">Пример</span><span class="sxs-lookup"><span data-stu-id="00fef-128">Example</span></span>  
 <span data-ttu-id="00fef-129">Другой метод получения того же результата состоит в использовании развернутых имен вместо объявления и создания объекта <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="00fef-129">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>  
  
 <span data-ttu-id="00fef-130">Этот подход влияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="00fef-130">This approach has performance implications.</span></span> <span data-ttu-id="00fef-131">Всякий раз при передаче [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] строки, содержащей развернутое имя, система [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] должна проанализировать это имя, обнаружить атомизированное пространство имен и атомарное имя.</span><span class="sxs-lookup"><span data-stu-id="00fef-131">Each time you pass a string that contains an expanded name to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="00fef-132">Этот процесс требует затрат процессорного времени.</span><span class="sxs-lookup"><span data-stu-id="00fef-132">This process takes CPU time.</span></span> <span data-ttu-id="00fef-133">Если производительность является важным фактором, целесообразнее объявить и использовать объект <xref:System.Xml.Linq.XNamespace> явным образом.</span><span class="sxs-lookup"><span data-stu-id="00fef-133">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>  
  
 <span data-ttu-id="00fef-134">Если производительность важна, дополнительные сведения см. в разделе [Предварительная атомизация объектов XName (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="00fef-134">If performance is an important issue, see [Pre-Atomization of XName Objects (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md) for more information</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="00fef-135">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="00fef-135">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00fef-136">См. также</span><span class="sxs-lookup"><span data-stu-id="00fef-136">See also</span></span>

- [<span data-ttu-id="00fef-137">Обзор пространств имен (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="00fef-137">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
