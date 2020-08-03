---
title: Поиск стиля абзаца по умолчанию (C#)
description: Узнайте, как обрабатывать документ WordprocessingML с помощью LINQ в C#. В этом примере выполняется поиск стиля абзацев по умолчанию в документе.
ms.date: 07/20/2015
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: e18bbbdbd5b2627c9ff4c3c3eedd84d7cb166a62
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103822"
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="331e4-104">Поиск стиля абзаца по умолчанию (C#)</span><span class="sxs-lookup"><span data-stu-id="331e4-104">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="331e4-105">Первая задача в учебнике "Обработка информации в документе WordprocessingML" заключается в поиске стиля абзацев по умолчанию в документе.</span><span class="sxs-lookup"><span data-stu-id="331e4-105">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="331e4-106">Пример</span><span class="sxs-lookup"><span data-stu-id="331e4-106">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="331e4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="331e4-107">Description</span></span>  
 <span data-ttu-id="331e4-108">В следующем примере открывается документ Office Open XML WordprocessingML, осуществляется поиск секций с документом и стилями в пакете, а затем выполняется запрос, который находит имя стиля по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="331e4-108">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="331e4-109">Сведения о пакетах документов Office Open XML и частях, из которых они состоят, см. в разделе [Сведения о документах WordprocessingML в формате Office Open XML (C#)](./wordprocessingml-document-with-styles.md).</span><span class="sxs-lookup"><span data-stu-id="331e4-109">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](./wordprocessingml-document-with-styles.md).</span></span>  
  
 <span data-ttu-id="331e4-110">Этот запрос находит узел с именем `w:style`, который имеет атрибут `w:type` со значением «paragraph», а также имеет атрибут `w:default` со значением «1».</span><span class="sxs-lookup"><span data-stu-id="331e4-110">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="331e4-111">Так как XML-узел с этими атрибутами будет только один, запрос использует оператор <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType>, чтобы преобразовать коллекцию в один элемент.</span><span class="sxs-lookup"><span data-stu-id="331e4-111">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="331e4-112">Затем он возвращает значение атрибута `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="331e4-112">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="331e4-113">В этом примере используются классы из сборки WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="331e4-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="331e4-114">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="331e4-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="331e4-115">Код</span><span class="sxs-lookup"><span data-stu-id="331e4-115">Code</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a><span data-ttu-id="331e4-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="331e4-116">Comments</span></span>  
 <span data-ttu-id="331e4-117">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="331e4-117">This example produces the following output:</span></span>  
  
```output  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="331e4-118">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="331e4-118">Next Steps</span></span>  
 <span data-ttu-id="331e4-119">В следующем примере будет создан похожий запрос, который ищет все абзацы в документе и их стили:</span><span class="sxs-lookup"><span data-stu-id="331e4-119">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
- [<span data-ttu-id="331e4-120">Извлечение абзацев и стилей (C#)</span><span class="sxs-lookup"><span data-stu-id="331e4-120">Retrieving the Paragraphs and Their Styles (C#)</span></span>](./retrieving-the-paragraphs-and-their-styles.md)  
