---
title: Ввод XPathDocument в XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
ms.openlocfilehash: 66cdbae8b52ca1b7ed46e8f040fcbf51c969dea2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282978"
---
# <a name="xpathdocument-input-to-xsltransform"></a>Ввод XPathDocument в XslTransform
Объект <xref:System.Xml.XPath.XPathDocument> является кэшем только для чтения, который предназначен для обработки документов с помощью <xref:System.Xml.Xsl.XslTransform>. Он структурно аналогичен модели XML DOM, но значительно оптимизирован для обработки XSLT и модели данных языка XPath с помощью функций оптимизации XPath в классе <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](migrating-from-the-xsltransform-class.md).  
  
 В следующем образце кода создается объект <xref:System.Xml.XPath.XPathDocument> в качестве входных данных для преобразования.  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a>См. также

- [Реализация классом XslTransform XSLT-процессора](xsltransform-class-implements-the-xslt-processor.md)
