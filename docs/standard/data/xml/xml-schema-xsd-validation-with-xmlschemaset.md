---
title: Проверка по XML-схеме (XSD) с помощью XmlSchemaSet
description: Сведения о том, как проверить XML-документы на соответствие схеме языка определения схемы XML (XSD) с помощью класса XmlSchemaSet в .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 995323d1882da13d45cdac516518d5b67845715a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594508"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="405c7-103">Проверка по XML-схеме (XSD) с помощью XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="405c7-103">XML schema (XSD) validation with XmlSchemaSet</span></span>

<span data-ttu-id="405c7-104">XML-документы можно проверять на соответствие схеме XML в классе <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="405c7-104">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validate-xml-documents"></a><span data-ttu-id="405c7-105">Проверка XML-документов</span><span class="sxs-lookup"><span data-stu-id="405c7-105">Validate XML documents</span></span>  
 <span data-ttu-id="405c7-106">Проверка XML-документов выполняется с помощью метода <xref:System.Xml.XmlReader.Create%2A> класса <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="405c7-106">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="405c7-107">Чтобы выполнить проверку XML-документа, создайте объект <xref:System.Xml.XmlReaderSettings>, содержащий схему XML, с помощью которой выполняется проверка XML-документа.</span><span class="sxs-lookup"><span data-stu-id="405c7-107">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="405c7-108">Пространство имен <xref:System.Xml.Schema> содержит методы расширений, которые упрощают проверку XML-дерева по файлу XSD при использовании [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) и [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="405c7-108">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="405c7-109">Дополнительные сведения о проверке XML-документов с помощью LINQ to XML см. в практических руководствах [Проверка с использованием XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) и [ Проверка с использованием XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="405c7-109">For more information on validating XML documents with LINQ to XML, see [How to validate using XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) and [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span></span>
  
 <span data-ttu-id="405c7-110">Отдельную схему или набор схем (например, класс <xref:System.Xml.Schema.XmlSchemaSet>) можно добавить в класс <xref:System.Xml.Schema.XmlSchemaSet>, передав ее в качестве параметра метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> метод <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="405c7-110">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="405c7-111">При проверке документа целевое пространство имен документа должно соответствовать целевому пространству имен схемы в наборе схем.</span><span class="sxs-lookup"><span data-stu-id="405c7-111">When validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="405c7-112">Далее приведен пример XML-документа.</span><span class="sxs-lookup"><span data-stu-id="405c7-112">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="405c7-113">Далее приведена схема, по которой проверяется XML-документ из примера.</span><span class="sxs-lookup"><span data-stu-id="405c7-113">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="405c7-114">В следующем примере кода приведенная выше схема добавляется к свойству <xref:System.Xml.XmlReaderSettings.Schemas%2A> объекта <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="405c7-114">In the code example that follows, the schema above is added to the <xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="405c7-115">Объект <xref:System.Xml.XmlReaderSettings> передается в качестве параметра в метод <xref:System.Xml.XmlReader.Create%2A> объекта <xref:System.Xml.XmlReader>, который проверяет XML-документ.</span><span class="sxs-lookup"><span data-stu-id="405c7-115">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="405c7-116">Свойство <xref:System.Xml.XmlReaderSettings.ValidationType%2A> объекта <xref:System.Xml.XmlReaderSettings> устанавливается в `Schema`, чтобы включить проверку XML-документа в методе <xref:System.Xml.XmlReader.Create%2A> объекта <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="405c7-116">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="405c7-117">Обработчик <xref:System.Xml.Schema.ValidationEventHandler> добавляется в объект <xref:System.Xml.XmlReaderSettings>, чтобы обрабатывать все события <xref:System.Xml.Schema.XmlSeverityType.Warning> или <xref:System.Xml.Schema.XmlSeverityType.Error>, вызванные в результате ошибок, найденных при проверке XML-документа и схемы.</span><span class="sxs-lookup"><span data-stu-id="405c7-117">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example #1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="405c7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="405c7-118">See also</span></span>

- [<span data-ttu-id="405c7-119">XmlSchemaSet для компиляции схемы</span><span class="sxs-lookup"><span data-stu-id="405c7-119">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="405c7-120">Работа с XML-схемами</span><span class="sxs-lookup"><span data-stu-id="405c7-120">Working with XML Schemas</span></span>](working-with-xml-schemas.md)
