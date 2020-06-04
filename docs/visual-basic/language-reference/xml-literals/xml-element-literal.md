---
title: XML-литерал элемента
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6a91de4e279816bafd29f46bb4f5422cbd934ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400193"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="69a85-102">Литеральное представление XML-элемента (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69a85-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="69a85-103">Литерал, представляющий <xref:System.Xml.Linq.XElement> объект.</span><span class="sxs-lookup"><span data-stu-id="69a85-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="69a85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69a85-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="69a85-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="69a85-105">Parts</span></span>

- `<`

  <span data-ttu-id="69a85-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="69a85-106">Required.</span></span> <span data-ttu-id="69a85-107">Открывает начальный тег элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="69a85-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="69a85-108">Required.</span></span> <span data-ttu-id="69a85-109">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-109">Name of the element.</span></span> <span data-ttu-id="69a85-110">Формат может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="69a85-110">The format is one of the following:</span></span>

  - <span data-ttu-id="69a85-111">Литеральный текст для имени элемента в форме `[ePrefix:]eName` , где:</span><span class="sxs-lookup"><span data-stu-id="69a85-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="69a85-112">Часть</span><span class="sxs-lookup"><span data-stu-id="69a85-112">Part</span></span>|<span data-ttu-id="69a85-113">Описание</span><span class="sxs-lookup"><span data-stu-id="69a85-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="69a85-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69a85-114">Optional.</span></span> <span data-ttu-id="69a85-115">Префикс пространства имен XML для элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="69a85-116">Должно быть глобальным пространством имен XML, которое определено с помощью `Imports` инструкции в файле или на уровне проекта, или локального пространства имен XML, определенного в этом элементе или в родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="69a85-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="69a85-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="69a85-117">Required.</span></span> <span data-ttu-id="69a85-118">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-118">Name of the element.</span></span> <span data-ttu-id="69a85-119">Формат может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="69a85-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="69a85-120">— Литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="69a85-120">- Literal text.</span></span> <span data-ttu-id="69a85-121">См. [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="69a85-121">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="69a85-122">— Внедренное выражение формы `<%= eNameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="69a85-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="69a85-123">Тип `eNameExp` должен быть `String` или типом, неявно преобразуемым в <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="69a85-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="69a85-124">Внедренное выражение формы `<%= nameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="69a85-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="69a85-125">Тип `nameExp` должен быть `String` или типом, неявно преобразуемым в <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="69a85-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="69a85-126">Внедренное выражение не допускается в закрывающем теге элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="69a85-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69a85-127">Optional.</span></span> <span data-ttu-id="69a85-128">Список атрибутов, объявленных в литерале.</span><span class="sxs-lookup"><span data-stu-id="69a85-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="69a85-129">Каждый `attribute` из них имеет один из следующих синтаксисов:</span><span class="sxs-lookup"><span data-stu-id="69a85-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="69a85-130">Назначение атрибута в форме `[aPrefix:]aName=aValue` , где:</span><span class="sxs-lookup"><span data-stu-id="69a85-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="69a85-131">Часть</span><span class="sxs-lookup"><span data-stu-id="69a85-131">Part</span></span>|<span data-ttu-id="69a85-132">Описание</span><span class="sxs-lookup"><span data-stu-id="69a85-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="69a85-133">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69a85-133">Optional.</span></span> <span data-ttu-id="69a85-134">Префикс пространства имен XML для атрибута.</span><span class="sxs-lookup"><span data-stu-id="69a85-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="69a85-135">Должно быть глобальным пространством имен XML, определенным `Imports` в операторе, или локальным пространством имен XML, которое определено в этом элементе или в родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="69a85-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="69a85-136">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="69a85-136">Required.</span></span> <span data-ttu-id="69a85-137">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="69a85-137">Name of the attribute.</span></span> <span data-ttu-id="69a85-138">Формат может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="69a85-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="69a85-139">— Литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="69a85-139">- Literal text.</span></span> <span data-ttu-id="69a85-140">См. [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="69a85-140">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="69a85-141">— Внедренное выражение формы `<%= aNameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="69a85-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="69a85-142">Тип `aNameExp` должен быть `String` или типом, неявно преобразуемым в <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="69a85-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="69a85-143">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69a85-143">Optional.</span></span> <span data-ttu-id="69a85-144">Значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="69a85-144">Value of the attribute.</span></span> <span data-ttu-id="69a85-145">Формат может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="69a85-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="69a85-146">— Литеральный текст, заключенный в кавычки.</span><span class="sxs-lookup"><span data-stu-id="69a85-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="69a85-147">— Внедренное выражение формы `<%= aValueExp %>` .</span><span class="sxs-lookup"><span data-stu-id="69a85-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="69a85-148">Разрешен любой тип.</span><span class="sxs-lookup"><span data-stu-id="69a85-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="69a85-149">Внедренное выражение формы `<%= aExp %>` .</span><span class="sxs-lookup"><span data-stu-id="69a85-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="69a85-150">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69a85-150">Optional.</span></span> <span data-ttu-id="69a85-151">Указывает, что элемент является пустым элементом без содержимого.</span><span class="sxs-lookup"><span data-stu-id="69a85-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="69a85-152">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="69a85-152">Required.</span></span> <span data-ttu-id="69a85-153">Завершает начальный или пустой тег элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="69a85-154">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69a85-154">Optional.</span></span> <span data-ttu-id="69a85-155">Содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="69a85-156">Каждый `content` из них может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="69a85-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="69a85-157">Текст литерала.</span><span class="sxs-lookup"><span data-stu-id="69a85-157">Literal text.</span></span> <span data-ttu-id="69a85-158">Все пробелы в `elementContents` значительной мере имеют литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="69a85-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="69a85-159">Внедренное выражение формы `<%= contentExp %>` .</span><span class="sxs-lookup"><span data-stu-id="69a85-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="69a85-160">Литерал XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-160">XML element literal.</span></span>

  - <span data-ttu-id="69a85-161">XML-литерал комментария.</span><span class="sxs-lookup"><span data-stu-id="69a85-161">XML comment literal.</span></span> <span data-ttu-id="69a85-162">См. [XML-литерал комментария](xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="69a85-162">See [XML Comment Literal](xml-comment-literal.md).</span></span>

  - <span data-ttu-id="69a85-163">Литерал инструкции обработки XML.</span><span class="sxs-lookup"><span data-stu-id="69a85-163">XML processing instruction literal.</span></span> <span data-ttu-id="69a85-164">См. раздел [XML-текст инструкции по обработке](xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="69a85-164">See [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="69a85-165">XML-литерал CDATA.</span><span class="sxs-lookup"><span data-stu-id="69a85-165">XML CDATA literal.</span></span> <span data-ttu-id="69a85-166">См. [XML CDATA Literal](xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="69a85-166">See [XML CDATA Literal](xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="69a85-167">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69a85-167">Optional.</span></span> <span data-ttu-id="69a85-168">Представляет закрывающий тег для элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="69a85-169">Необязательный `name` параметр не допускается, если он является результатом внедренного выражения.</span><span class="sxs-lookup"><span data-stu-id="69a85-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="69a85-170">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="69a85-170">Return Value</span></span>

<span data-ttu-id="69a85-171">Объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="69a85-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="69a85-172">Комментарии</span><span class="sxs-lookup"><span data-stu-id="69a85-172">Remarks</span></span>

<span data-ttu-id="69a85-173">Для создания объектов в коде можно использовать синтаксис литерала XML-элемента <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="69a85-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="69a85-174">XML-литерал может охватывать несколько строк без использования символов продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="69a85-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="69a85-175">Эта функция позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.</span><span class="sxs-lookup"><span data-stu-id="69a85-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="69a85-176">Внедренные выражения формы `<%= exp %>` позволяют добавлять динамическую информацию в литерал XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="69a85-177">Дополнительные сведения см. [в разделе внедренные выражения в XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="69a85-177">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="69a85-178">Компилятор Visual Basic преобразует литерал XML-элемента в вызовы <xref:System.Xml.Linq.XElement.%23ctor%2A> конструктора и, если это необходимо, <xref:System.Xml.Linq.XAttribute.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="69a85-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="69a85-179">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="69a85-179">XML Namespaces</span></span>

<span data-ttu-id="69a85-180">Префиксы пространства имен XML полезны, когда необходимо создать XML-литералы с элементами из одного и того же пространства имен много раз в коде.</span><span class="sxs-lookup"><span data-stu-id="69a85-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="69a85-181">Можно использовать глобальные префиксы пространства имен XML, которые определяются с помощью `Imports` инструкции или локальных префиксов, которые определяются с помощью `xmlns:xmlPrefix="xmlNamespace"` синтаксиса атрибута.</span><span class="sxs-lookup"><span data-stu-id="69a85-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="69a85-182">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="69a85-182">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="69a85-183">В соответствии с правилами области для пространств имен XML локальные префиксы имеют приоритет над глобальными префиксами.</span><span class="sxs-lookup"><span data-stu-id="69a85-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="69a85-184">Однако если XML-литерал определяет пространство имен XML, это пространство имен недоступно для выражений, которые отображаются во внедренном выражении.</span><span class="sxs-lookup"><span data-stu-id="69a85-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="69a85-185">Внедренное выражение может обращаться только к глобальному пространству имен XML.</span><span class="sxs-lookup"><span data-stu-id="69a85-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="69a85-186">Компилятор Visual Basic преобразует каждое глобальное пространство имен XML, используемое XML-литералом, в одно локальное определение пространства имен в созданном коде.</span><span class="sxs-lookup"><span data-stu-id="69a85-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="69a85-187">Глобальные пространства имен XML, которые не используются, не отображаются в созданном коде.</span><span class="sxs-lookup"><span data-stu-id="69a85-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="69a85-188">Пример</span><span class="sxs-lookup"><span data-stu-id="69a85-188">Example</span></span>

<span data-ttu-id="69a85-189">В следующем примере показано, как создать простой XML-элемент с двумя вложенными пустыми элементами.</span><span class="sxs-lookup"><span data-stu-id="69a85-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="69a85-190">В примере отображается следующий текст.</span><span class="sxs-lookup"><span data-stu-id="69a85-190">The example displays the following text.</span></span> <span data-ttu-id="69a85-191">Обратите внимание, что литерал сохраняет структуру пустых элементов.</span><span class="sxs-lookup"><span data-stu-id="69a85-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="69a85-192">Пример</span><span class="sxs-lookup"><span data-stu-id="69a85-192">Example</span></span>

<span data-ttu-id="69a85-193">В следующем примере показано, как использовать внедренные выражения для именования элемента и создания атрибутов.</span><span class="sxs-lookup"><span data-stu-id="69a85-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="69a85-194">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="69a85-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="69a85-195">Пример</span><span class="sxs-lookup"><span data-stu-id="69a85-195">Example</span></span>

<span data-ttu-id="69a85-196">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="69a85-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="69a85-197">Затем он использует префикс пространства имен для создания XML-литерала и отображает окончательную форму элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="69a85-198">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="69a85-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="69a85-199">Обратите внимание, что компилятор преобразует префикс глобального пространства имен XML в определение префикса для пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="69a85-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="69a85-200">\<ns:middle>Элемент переопределяет префикс пространства имен XML для \<ns:inner1> элемента.</span><span class="sxs-lookup"><span data-stu-id="69a85-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="69a85-201">Однако \<ns:inner2> элемент использует пространство имен, определенное `Imports` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="69a85-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="69a85-202">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="69a85-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="69a85-203">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="69a85-203">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="69a85-204">XML-литерал комментария</span><span class="sxs-lookup"><span data-stu-id="69a85-204">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="69a85-205">XML-литерал CDATA</span><span class="sxs-lookup"><span data-stu-id="69a85-205">XML CDATA Literal</span></span>](xml-cdata-literal.md)
- [<span data-ttu-id="69a85-206">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="69a85-206">XML Literals</span></span>](index.md)
- [<span data-ttu-id="69a85-207">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69a85-207">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="69a85-208">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="69a85-208">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="69a85-209">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="69a85-209">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
