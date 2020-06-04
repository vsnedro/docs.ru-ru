---
title: Встроенные выражения в XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: d4ff9442aa82a3eb46d56500159562174646ea58
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410261"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="cbd0c-102">Встроенные выражения в XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbd0c-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="cbd0c-103">Внедренные выражения позволяют создавать XML-литералы, содержащие выражения, вычисляемые во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="cbd0c-104">Синтаксис для внедренного выражения — это `<%=` `expression` `%>` то же, что и синтаксис, используемый в ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="cbd0c-105">Например, можно создать литерал XML-элемента, объединяющий внедренные выражения с текстовым содержимым.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="cbd0c-106">Если `isbnNumber` содержит целое число 12345 и `modifiedDate` содержит дату 3/5/2006, то при выполнении этого кода значение `book` равно:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="cbd0c-107">Расположение и проверка внедренных выражений</span><span class="sxs-lookup"><span data-stu-id="cbd0c-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="cbd0c-108">Встроенные выражения могут использоваться только в определенных местах в выражениях литералов XML.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="cbd0c-109">Расположение выражения определяет, какие типы могут быть возвращены выражением и как `Nothing` обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="cbd0c-110">В следующей таблице описаны допустимые расположения и типы внедренных выражений.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="cbd0c-111">Расположение в литерале</span><span class="sxs-lookup"><span data-stu-id="cbd0c-111">Location in literal</span></span>|<span data-ttu-id="cbd0c-112">Тип выражения</span><span class="sxs-lookup"><span data-stu-id="cbd0c-112">Type of expression</span></span>|<span data-ttu-id="cbd0c-113">Обработка`Nothing`</span><span class="sxs-lookup"><span data-stu-id="cbd0c-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="cbd0c-114">Имя XML-элемента</span><span class="sxs-lookup"><span data-stu-id="cbd0c-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="cbd0c-115">Ошибка</span><span class="sxs-lookup"><span data-stu-id="cbd0c-115">Error</span></span>|  
|<span data-ttu-id="cbd0c-116">Содержимое XML-элемента</span><span class="sxs-lookup"><span data-stu-id="cbd0c-116">XML element content</span></span>|<span data-ttu-id="cbd0c-117">`Object`или массив`Object`</span><span class="sxs-lookup"><span data-stu-id="cbd0c-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="cbd0c-118">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="cbd0c-118">Ignored</span></span>|  
|<span data-ttu-id="cbd0c-119">Имя атрибута XML-элемента</span><span class="sxs-lookup"><span data-stu-id="cbd0c-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="cbd0c-120">Ошибка, если значение атрибута также не равно`Nothing`</span><span class="sxs-lookup"><span data-stu-id="cbd0c-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="cbd0c-121">Значение атрибута XML-элемента</span><span class="sxs-lookup"><span data-stu-id="cbd0c-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="cbd0c-122">Объявление атрибута пропущено</span><span class="sxs-lookup"><span data-stu-id="cbd0c-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="cbd0c-123">Атрибут XML-элемента</span><span class="sxs-lookup"><span data-stu-id="cbd0c-123">XML element attribute</span></span>|<span data-ttu-id="cbd0c-124"><xref:System.Xml.Linq.XAttribute>или коллекция<xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="cbd0c-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="cbd0c-125">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="cbd0c-125">Ignored</span></span>|  
|<span data-ttu-id="cbd0c-126">Корневой элемент XML-документа</span><span class="sxs-lookup"><span data-stu-id="cbd0c-126">XML document root element</span></span>|<span data-ttu-id="cbd0c-127"><xref:System.Xml.Linq.XElement>или коллекция из одного <xref:System.Xml.Linq.XElement> объекта и произвольное число <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment> объектов и</span><span class="sxs-lookup"><span data-stu-id="cbd0c-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="cbd0c-128">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="cbd0c-128">Ignored</span></span>|  
  
- <span data-ttu-id="cbd0c-129">Пример внедренного выражения в имени XML-элемента:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="cbd0c-130">Пример внедренного выражения в содержимом XML-элемента:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="cbd0c-131">Пример внедренного выражения в имени атрибута XML-элемента:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="cbd0c-132">Пример внедренного выражения в значении атрибута XML-элемента:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="cbd0c-133">Пример внедренного выражения в атрибуте XML-элемента:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="cbd0c-134">Пример внедренного выражения в корневом элементе XML-документа:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="cbd0c-135">Если включить `Option Strict` , компилятор проверяет, что тип каждого внедренного выражения расширяется до требуемого типа.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="cbd0c-136">Единственным исключением является корневой элемент XML-документа, который проверяется при выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="cbd0c-137">При компиляции без `Option Strict` можно внедрить выражения типа `Object` и их тип проверяется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="cbd0c-138">В расположениях, где содержимое является необязательным, внедренные выражения, содержащие, `Nothing` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="cbd0c-139">Это означает, что нет необходимости проверять содержимое элемента, значения атрибутов и элементы массива `Nothing` перед использованием XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="cbd0c-140">Обязательные значения, такие как имена элементов и атрибутов, не могут иметь значение `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="cbd0c-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="cbd0c-141">Дополнительные сведения об использовании внедренных выражений в определенном типе литерала см. в разделе [литерал XML-документа](../../../language-reference/xml-literals/xml-document-literal.md), [литерал XML-элемента](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="cbd0c-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="cbd0c-142">Правила области видимости</span><span class="sxs-lookup"><span data-stu-id="cbd0c-142">Scoping Rules</span></span>  
 <span data-ttu-id="cbd0c-143">Компилятор преобразует каждый XML-литерал в вызов конструктора для соответствующего типа литерала.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="cbd0c-144">Литеральное содержимое и внедренные выражения в XML-литерале передаются в качестве аргументов в конструктор.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="cbd0c-145">Это означает, что все элементы программирования Visual Basic, доступные для XML-литерала, также доступны для внедренных выражений.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="cbd0c-146">В XML-литерале можно получить доступ к префиксам пространства имен XML, объявленным с помощью `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="cbd0c-147">Можно объявить новый префикс пространства имен XML или затенить существующий префикс пространства имен XML в элементе с помощью `xmlns` атрибута.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="cbd0c-148">Новое пространство имен доступно для дочерних узлов этого элемента, но не для XML-литералов во внедренных выражениях.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbd0c-149">При объявлении префикса пространства имен XML с помощью `xmlns` атрибута Namespace значение атрибута должно быть строковой константой.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="cbd0c-150">В этом отношении использование `xmlns` атрибута аналогично использованию `Imports` оператора для объявления пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="cbd0c-151">Нельзя использовать внедренное выражение для указания значения пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd0c-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cbd0c-152">See also</span></span>

- [<span data-ttu-id="cbd0c-153">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cbd0c-153">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="cbd0c-154">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="cbd0c-154">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="cbd0c-155">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="cbd0c-155">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="cbd0c-156">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="cbd0c-156">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="cbd0c-157">Оператор Imports (пространство имен .NET и тип)</span><span class="sxs-lookup"><span data-stu-id="cbd0c-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="cbd0c-158">Общие сведения об XML-литералах</span><span class="sxs-lookup"><span data-stu-id="cbd0c-158">XML Literals Overview</span></span>](xml-literals-overview.md)
