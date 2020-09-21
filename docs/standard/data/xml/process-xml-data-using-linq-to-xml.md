---
title: Обработка XML-данных с помощью LINQ to XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 059d6b9d-63f7-4011-9ba8-8406f0bbae7d
ms.openlocfilehash: 5afa9fc84b7f41023eceb5c0734b0667dc55514e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556503"
---
# <a name="process-xml-data-using-linq-to-xml"></a><span data-ttu-id="86d33-102">Обработка XML-данных с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="86d33-102">Process XML Data Using LINQ to XML</span></span>
<span data-ttu-id="86d33-103">LINQ to XML - новая модель для обработки XML-данных в платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="86d33-103">LINQ to XML is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="86d33-104">С помощью LINQ to XML разработчик может выполнять над XML-данными любые операции: запросы, изменения, создание, сохранение и сериализацию XML-документов.</span><span class="sxs-lookup"><span data-stu-id="86d33-104">LINQ to XML allows developers to do everything they would expect with XML data: querying, modifying, creating, saving, and serializing XML documents.</span></span> <span data-ttu-id="86d33-105">Основные преимущества заключаются в возможностях запросов и создания.</span><span class="sxs-lookup"><span data-stu-id="86d33-105">The real advantages lie in the query and creation capabilities.</span></span>  
  
 <span data-ttu-id="86d33-106">Синтаксис запросов LINQ to XML краток и выразителен, он даже больше похож на SQL, чем на XPath или XQuery.</span><span class="sxs-lookup"><span data-stu-id="86d33-106">Queries in LINQ to XML are succinct and expressive, using syntax more similar to SQL than to XPath or XQuery.</span></span> <span data-ttu-id="86d33-107">Поскольку результаты запросов могут возвращаться как коллекции элементов или атрибутов, либо использоваться как параметры для объектов XElement, XML-деревья очень просто преобразовывать из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="86d33-107">Because query results can be returned as collections of elements or attributes and can be used as parameters for XElement objects, XML trees can be easily transformed from one shape to another.</span></span>  
  
 <span data-ttu-id="86d33-108">В LINQ to XML используется технология интегрированного в язык запроса (LINQ) на платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="86d33-108">LINQ to XML leverages the language-integrated query (LINQ) technology in the .NET Framework version 3.5.</span></span> <span data-ttu-id="86d33-109">LINQ расширяет синтаксис C# и Visual Basic, обеспечивая мощные возможности запросов, которые потенциально могут охватить любое хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="86d33-109">LINQ extends the language syntax of C# and Visual Basic to provide powerful query capabilities that can be extended to potentially any data store.</span></span>  
  
 <span data-ttu-id="86d33-110">Подробное описание использования см. в разделах [LINQ to XML (C#)](../../linq/linq-xml-overview.md) и [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d33-110">For a detailed discussion of its use, see [LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span></span> <span data-ttu-id="86d33-111">Общие сведения о платформе LINQ см. в разделе [LINQ — C#](../../../csharp/programming-guide/concepts/linq/index.md) или [LINQ — Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="86d33-111">For an overview of the LINQ framework, see [Language-Integrated Query (LINQ) - C#](../../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d33-112">См. также</span><span class="sxs-lookup"><span data-stu-id="86d33-112">See also</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Linq>
- [<span data-ttu-id="86d33-113">Сравнение LINQ to XML с моделью DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="86d33-113">LINQ to XML vs. DOM (C#)</span></span>](../../linq/linq-xml-vs-dom.md)
- [<span data-ttu-id="86d33-114">Сравнение LINQ to XML с DOM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86d33-114">LINQ to XML vs. DOM (Visual Basic)</span></span>](../../linq/linq-xml-vs-dom.md)
- [<span data-ttu-id="86d33-115">Сравнение LINQ to XML с другими XML-технологиями (C#)</span><span class="sxs-lookup"><span data-stu-id="86d33-115">LINQ to XML vs. Other XML Technologies (C#)</span></span>](../../linq/linq-xml-vs-xml-technologies.md)
- [<span data-ttu-id="86d33-116">Сравнение LINQ to XML с другими XML-технологиями (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86d33-116">LINQ to XML vs. Other XML Technologies (Visual Basic)</span></span>](../../linq/linq-xml-vs-xml-technologies.md)
