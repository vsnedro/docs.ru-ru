---
title: Извлечение абзацев и стилей (C#)
description: Узнайте, как составить запрос, который позволяет извлечь абзацы и определить стиль каждого из них.
ms.date: 07/20/2015
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 94d01a13485f70bc9d9cef55b5f390c3b30d7f14
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303404"
---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a><span data-ttu-id="39cdb-103">Извлечение абзацев и стилей (C#)</span><span class="sxs-lookup"><span data-stu-id="39cdb-103">Retrieving the Paragraphs and Their Styles (C#)</span></span>
<span data-ttu-id="39cdb-104">В этом примере составляется запрос, при котором получаются узлы абзацев из документа WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="39cdb-104">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="39cdb-105">Также идентифицируется стиль каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="39cdb-105">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="39cdb-106">Этот запрос основан на запросе из предыдущего примера — [Поиск стиля абзаца по умолчанию (C#)](./finding-the-default-paragraph-style.md), который получает стиль по умолчанию из списка стилей.</span><span class="sxs-lookup"><span data-stu-id="39cdb-106">This query builds on the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="39cdb-107">Эти сведения требуются для того, чтобы запрос мог идентифицировать стиль абзацев, для которых явно не установлен стиль.</span><span class="sxs-lookup"><span data-stu-id="39cdb-107">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="39cdb-108">Стили абзацев устанавливаются при помощи элемента `w:pPr`. Если абзац не содержит этот элемент, выполняется форматирование стилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="39cdb-108">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="39cdb-109">В этом разделе объясняется значение некоторых фрагментов запроса, после чего запрос показывается в составе целостного рабочего примера.</span><span class="sxs-lookup"><span data-stu-id="39cdb-109">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39cdb-110">Пример</span><span class="sxs-lookup"><span data-stu-id="39cdb-110">Example</span></span>  
 <span data-ttu-id="39cdb-111">Источник этого запроса по получению всех абзацев документа и их стилей таков:</span><span class="sxs-lookup"><span data-stu-id="39cdb-111">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 <span data-ttu-id="39cdb-112">Это выражение напоминает источник запроса предыдущего примера — [Поиск стиля абзаца по умолчанию (C#)](./finding-the-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="39cdb-112">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="39cdb-113">Основная разница в том, что здесь используется ось <xref:System.Xml.Linq.XContainer.Descendants%2A> вместо оси <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="39cdb-113">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="39cdb-114">В запросе используется ось <xref:System.Xml.Linq.XContainer.Descendants%2A>, поскольку в документах, в которых имеются разделы, абзацы не будут прямыми потомками элемента текста, а будут находиться на два уровня ниже в иерархии.</span><span class="sxs-lookup"><span data-stu-id="39cdb-114">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="39cdb-115">За счет использования оси <xref:System.Xml.Linq.XContainer.Descendants%2A> этот код будет работать вне зависимости от того, используются разделы или нет.</span><span class="sxs-lookup"><span data-stu-id="39cdb-115">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39cdb-116">Пример</span><span class="sxs-lookup"><span data-stu-id="39cdb-116">Example</span></span>  
 <span data-ttu-id="39cdb-117">В этом разделе используется предложение `let`, чтобы определить элемент, содержащий узел стиля.</span><span class="sxs-lookup"><span data-stu-id="39cdb-117">The query uses a `let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="39cdb-118">Если элемент не найден, то `styleNode` устанавливается в значение `null`:</span><span class="sxs-lookup"><span data-stu-id="39cdb-118">If there is no element, then `styleNode` is set to `null`:</span></span>  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 <span data-ttu-id="39cdb-119">Предложение `let` сначала использует ось <xref:System.Xml.Linq.XContainer.Elements%2A> для поиска всех элементов с названием `pPr`, затем использует метод расширений <xref:System.Xml.Linq.Extensions.Elements%2A> для поиска всех дочерних элементов с названием `pStyle` и затем использует стандартный оператор запросов <xref:System.Linq.Enumerable.FirstOrDefault%2A> для объединения коллекции в одно целое.</span><span class="sxs-lookup"><span data-stu-id="39cdb-119">The `let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="39cdb-120">Если коллекция пуста, `styleNode` устанавливается в значение `null`.</span><span class="sxs-lookup"><span data-stu-id="39cdb-120">If the collection is empty, `styleNode` is set to `null`.</span></span> <span data-ttu-id="39cdb-121">Это выражение полезно для поиска потомков узла `pStyle`.</span><span class="sxs-lookup"><span data-stu-id="39cdb-121">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="39cdb-122">Обратите внимание, что, если дочерний узел `pPr` не существует, код продолжает работать, а не выводит исключение. Вместо этого узел `styleNode` устанавливается в значение `null`, что именно и требуется для предложения `let`.</span><span class="sxs-lookup"><span data-stu-id="39cdb-122">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `null`, which is the desired behavior of this `let` clause.</span></span>  
  
 <span data-ttu-id="39cdb-123">В этом запросе выполняется проецирование коллекции анонимного типа с двумя членами, `StyleName` и `ParagraphNode`.</span><span class="sxs-lookup"><span data-stu-id="39cdb-123">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39cdb-124">Пример</span><span class="sxs-lookup"><span data-stu-id="39cdb-124">Example</span></span>  
 <span data-ttu-id="39cdb-125">В данном примере обрабатывается документ WordprocessingML, из которого извлекаются узлы абзацев.</span><span class="sxs-lookup"><span data-stu-id="39cdb-125">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="39cdb-126">Также идентифицируется стиль каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="39cdb-126">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="39cdb-127">Этот пример основан на предыдущих примерах данного учебника.</span><span class="sxs-lookup"><span data-stu-id="39cdb-127">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="39cdb-128">Новый запрос выявляется в комментариях в нижеприведенном коде.</span><span class="sxs-lookup"><span data-stu-id="39cdb-128">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="39cdb-129">Инструкции по созданию исходного документа для данного примера можно найти в разделе [Создание исходного документа в формате Office Open XML (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="39cdb-129">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="39cdb-130">В этом примере используются классы, находящиеся в сборке WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="39cdb-130">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="39cdb-131">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39cdb-131">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
string defaultStyle =
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 <span data-ttu-id="39cdb-132">Этот пример выводит следующие результаты, будучи примененным к документу, описанному в разделе [Создание исходного документа в формате Office Open XML (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="39cdb-132">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
```output  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a><span data-ttu-id="39cdb-133">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="39cdb-133">Next Steps</span></span>  
 <span data-ttu-id="39cdb-134">В следующем разделе [Извлечение текста абзацев (C#)](./retrieving-the-text-of-the-paragraphs.md) вы создадите запрос для извлечение текста абзацев.</span><span class="sxs-lookup"><span data-stu-id="39cdb-134">In the next topic, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39cdb-135">См. также</span><span class="sxs-lookup"><span data-stu-id="39cdb-135">See also</span></span>

- [<span data-ttu-id="39cdb-136">Учебник. Обработка содержимого документа WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="39cdb-136">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
