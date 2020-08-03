---
title: Практическое руководство. Перехват ошибок анализа (C#)
description: В этом примере LINQ to XML в C# показано обнаружение неправильно сформированного или недопустимого кода XML. LINQ to XML использует XmlReader, который вызывает исключение при обнаружении неправильно сформированного или недопустимого кода XML.
ms.date: 07/20/2015
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: 0a891097322ef6acce062ea927692b01cc425e6c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105407"
---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="19f84-104">Практическое руководство. Перехват ошибок анализа (C#)</span><span class="sxs-lookup"><span data-stu-id="19f84-104">How to catch parsing errors (C#)</span></span>
<span data-ttu-id="19f84-105">В этом разделе показано, как обнаружить код XML, имеющий неправильный формат или не прошедший проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="19f84-105">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 <span data-ttu-id="19f84-106">Технология [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] реализуется с помощью объекта <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="19f84-106">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="19f84-107">Если средствам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] передается код XML, имеющий неправильный формат или не прошедший проверку правильности, то в базовом классе <xref:System.Xml.XmlReader> активизируется исключение.</span><span class="sxs-lookup"><span data-stu-id="19f84-107">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="19f84-108">Различные методы, выполняющие синтаксический анализ XML, например <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, не перехватывают это исключение; его можно перехватить позднее в приложении.</span><span class="sxs-lookup"><span data-stu-id="19f84-108">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19f84-109">Пример</span><span class="sxs-lookup"><span data-stu-id="19f84-109">Example</span></span>  
 <span data-ttu-id="19f84-110">В следующем коде предпринимается попытка выполнить синтаксический анализ кода XML, не прошедшего проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="19f84-110">The following code tries to parse invalid XML:</span></span>  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 <span data-ttu-id="19f84-111">При выполнении этого кода активизируется следующее исключение.</span><span class="sxs-lookup"><span data-stu-id="19f84-111">When you run this code, it throws the following exception:</span></span>  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="19f84-112">Сведения об исключениях, которые могут возникать при использовании методов <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> и <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> см. в документации <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="19f84-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  