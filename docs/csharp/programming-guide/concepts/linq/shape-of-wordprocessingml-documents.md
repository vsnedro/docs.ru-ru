---
title: Форма документов WordprocessingML (C#)
description: Сведения о формате документа WordprocessingML. Несколько примеров на C#, в которых используется документ WordprocessingML.
ms.date: 07/20/2015
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: 4a7716d775a634c5ad3719714be68fce67d5cbfe
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302351"
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="06261-104">Форма документов WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="06261-104">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="06261-105">Этот раздел позволяет ознакомиться с формой XML документов WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="06261-105">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="06261-106">Форматы Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="06261-106">Microsoft Office Formats</span></span>  
 <span data-ttu-id="06261-107">Собственным форматом файлов для выпуска 2007 системы Microsoft Office является Office Open XML (который обычно называют Open XML).</span><span class="sxs-lookup"><span data-stu-id="06261-107">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="06261-108">Open XML - это формат на основе XML, определенный стандартом Ecma, который в настоящее время проходит стандартизацию в организации ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="06261-108">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="06261-109">Язык разметки для файлов обработки текста в системе Open XML называется WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="06261-109">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="06261-110">В этом учебнике в качестве входных данных для примеров используются исходные файлы WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="06261-110">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="06261-111">При использовании Microsoft Office 2003 документы можно сохранять в формате Office Open XML, если установлен пакет обеспечения совместимости Microsoft Office Compatibility Pack для форматов Word, Excel и PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="06261-111">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="06261-112">Форма документов WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="06261-112">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="06261-113">Прежде всего необходимо понять, какую форму имеют документы WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="06261-113">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="06261-114">Документ WordprocessingML содержит элемент body (с именем `w:body`), который включает абзацы документа.</span><span class="sxs-lookup"><span data-stu-id="06261-114">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="06261-115">Каждый абзац содержит один или несколько текстовых периодов (с именем `w:r`).</span><span class="sxs-lookup"><span data-stu-id="06261-115">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="06261-116">Каждый текстовый период содержит один или несколько текстовых фрагментов (с именем `w:t`).</span><span class="sxs-lookup"><span data-stu-id="06261-116">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="06261-117">Ниже приведен очень простой документ WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="06261-117">The following is a very simple WordprocessingML document:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<w:document  
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
xmlns:o="urn:schemas-microsoft-com:office:office"  
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
xmlns:v="urn:schemas-microsoft-com:vml"  
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
xmlns:w10="urn:schemas-microsoft-com:office:word"  
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is a paragraph.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is another paragraph.</w:t>  
      </w:r>  
    </w:p>  
  </w:body>  
</w:document>  
```  
  
 <span data-ttu-id="06261-118">В этом документе два абзаца.</span><span class="sxs-lookup"><span data-stu-id="06261-118">This document contains two paragraphs.</span></span> <span data-ttu-id="06261-119">Оба они содержат по одному текстовому периоду, каждый включает один текстовый фрагмент.</span><span class="sxs-lookup"><span data-stu-id="06261-119">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="06261-120">Самый простой способ просмотра содержимого документа WordprocessingML в форме XML состоит в создании документа Microsoft Word, сохранении этого документа и запуске следующей программы, выводящей код XML на консоль.</span><span class="sxs-lookup"><span data-stu-id="06261-120">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="06261-121">В этом примере используются классы, находящиеся в сборке WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="06261-121">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="06261-122">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="06261-122">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
using (Package wdPackage = Package.Open("SampleDoc.docx", FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship relationship =  
        wdPackage  
        .GetRelationshipsByType(documentRelationshipType)  
        .FirstOrDefault();  
    if (relationship != null)  
    {  
        Uri documentUri =  
            PackUriHelper.ResolvePartUri(  
                new Uri("/", UriKind.Relative),  
                relationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Get the officeDocument part from the package.  
        //  Load the XML in the part into an XDocument instance.  
        XDocument xdoc =  
            XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
        Console.WriteLine(xdoc.Root);  
    }  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="06261-123">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="06261-123">External resources</span></span>

- [<span data-ttu-id="06261-124">Знакомство с форматами файлов Office (2007) Open XML</span><span class="sxs-lookup"><span data-stu-id="06261-124">Introducing the Office (2007) Open XML File Formats</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205%28v=office.12%29)
- [<span data-ttu-id="06261-125">Общие сведения о WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="06261-125">Overview of WordprocessingML</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812%28v=office.11%29)
- [<span data-ttu-id="06261-126">Структура файла WordProcessingML</span><span class="sxs-lookup"><span data-stu-id="06261-126">Anatomy of a WordProcessingML File</span></span>](http://officeopenxml.com/anatomyofOOXML.php)
- [<span data-ttu-id="06261-127">Общие сведения о WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="06261-127">Introduction to WordprocessingML</span></span>](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)

## <a name="see-also"></a><span data-ttu-id="06261-128">См. также</span><span class="sxs-lookup"><span data-stu-id="06261-128">See also</span></span>

- [<span data-ttu-id="06261-129">Учебник. Обработка содержимого документа WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="06261-129">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
