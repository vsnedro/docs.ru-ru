---
title: Создание XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: a6a927c8dc1a4f3e38a99a1f730be68a2566d048
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090031"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="551f8-102">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="551f8-102">Creating XML in Visual Basic</span></span>

<span data-ttu-id="551f8-103">Visual Basic позволяет использовать *XML-литералы* непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="551f8-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="551f8-104">Синтаксис XML-литерала представляет [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекты и аналогичен синтаксису xml 1,0.</span><span class="sxs-lookup"><span data-stu-id="551f8-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="551f8-105">Это упрощает создание XML-элементов, документов и фрагментов программным способом, так как код имеет ту же структуру, что и окончательный XML.</span><span class="sxs-lookup"><span data-stu-id="551f8-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="551f8-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="551f8-106">In This Section</span></span>  
  
|<span data-ttu-id="551f8-107">Термин</span><span class="sxs-lookup"><span data-stu-id="551f8-107">Term</span></span>|<span data-ttu-id="551f8-108">Определение</span><span class="sxs-lookup"><span data-stu-id="551f8-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="551f8-109">Общие сведения об XML-литералах</span><span class="sxs-lookup"><span data-stu-id="551f8-109">XML Literals Overview</span></span>](xml-literals-overview.md)|<span data-ttu-id="551f8-110">Общие сведения о XML-литералах и их связи с [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="551f8-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="551f8-111">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="551f8-111">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)|<span data-ttu-id="551f8-112">Описывает использование внедренных выражений в XML-литералах.</span><span class="sxs-lookup"><span data-stu-id="551f8-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="551f8-113">Практическое руководство. Создание XML-литералов</span><span class="sxs-lookup"><span data-stu-id="551f8-113">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)|<span data-ttu-id="551f8-114">Описывает создание XML-элемента в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="551f8-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="551f8-115">Пробелы в XML-литералах</span><span class="sxs-lookup"><span data-stu-id="551f8-115">White Space in XML Literals</span></span>](white-space-in-xml-literals.md)|<span data-ttu-id="551f8-116">Описывает, как Visual Basic обрабатывает пробелы в XML-литералах.</span><span class="sxs-lookup"><span data-stu-id="551f8-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="551f8-117">XML-литералы и спецификация XML 1.0</span><span class="sxs-lookup"><span data-stu-id="551f8-117">XML Literals and the XML 1.0 Specification</span></span>](xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="551f8-118">Описывает, как синтаксис XML-литерала в Visual Basic относится к спецификации XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="551f8-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="551f8-119">Практическое руководство. Внедрение выражений в XML-литералы</span><span class="sxs-lookup"><span data-stu-id="551f8-119">How to: Embed Expressions in XML Literals</span></span>](how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="551f8-120">Описывает использование внедренных выражений в XML-литералах для создания содержимого во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="551f8-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="551f8-121">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="551f8-121">Names of Declared XML Elements and Attributes</span></span>](names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="551f8-122">Описывает правила именования XML-элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="551f8-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="551f8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="551f8-123">See also</span></span>

- [<span data-ttu-id="551f8-124">XML</span><span class="sxs-lookup"><span data-stu-id="551f8-124">XML</span></span>](index.md)
