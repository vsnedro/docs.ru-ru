---
title: Оператор GetXmlNamespace
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 660474c1193076755889fd885c1b78bec78f0a2c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873465"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="26a41-102">Оператор GetXmlNamespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26a41-102">GetXmlNamespace Operator (Visual Basic)</span></span>

<span data-ttu-id="26a41-103">Возвращает <xref:System.Xml.Linq.XNamespace> объект, соответствующий указанному префиксу пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="26a41-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a41-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26a41-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="26a41-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="26a41-105">Parts</span></span>  

 `xmlNamespacePrefix`  
 <span data-ttu-id="26a41-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="26a41-106">Optional.</span></span> <span data-ttu-id="26a41-107">Строка, определяющая префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="26a41-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="26a41-108">Если указано, эта строка должна быть допустимым идентификатором XML.</span><span class="sxs-lookup"><span data-stu-id="26a41-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="26a41-109">Дополнительные сведения см. в разделе [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="26a41-109">For more information, see [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="26a41-110">Если префикс не указан, возвращается пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="26a41-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="26a41-111">Если пространство имен по умолчанию не указано, возвращается пустое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="26a41-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26a41-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="26a41-112">Return Value</span></span>  

 <span data-ttu-id="26a41-113"><xref:System.Xml.Linq.XNamespace>Объект, соответствующий префиксу пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="26a41-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26a41-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="26a41-114">Remarks</span></span>  

 <span data-ttu-id="26a41-115">`GetXmlNamespace`Оператор возвращает <xref:System.Xml.Linq.XNamespace> объект, соответствующий префиксу пространства имен XML `xmlNamespacePrefix` .</span><span class="sxs-lookup"><span data-stu-id="26a41-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="26a41-116">Префиксы пространства имен XML можно использовать непосредственно в XML-литералах и свойствах осей XML.</span><span class="sxs-lookup"><span data-stu-id="26a41-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="26a41-117">Однако необходимо использовать `GetXmlNamespace` оператор для преобразования префикса пространства имен в <xref:System.Xml.Linq.XNamespace> объект, прежде чем его можно будет использовать в коде.</span><span class="sxs-lookup"><span data-stu-id="26a41-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="26a41-118">К объекту можно добавить неполное имя элемента <xref:System.Xml.Linq.XNamespace> для получения полного <xref:System.Xml.Linq.XName> объекта, который [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] требуется многим методам.</span><span class="sxs-lookup"><span data-stu-id="26a41-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26a41-119">Пример</span><span class="sxs-lookup"><span data-stu-id="26a41-119">Example</span></span>  

 <span data-ttu-id="26a41-120">В следующем примере `ns` выполняется импорт в виде префикса пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="26a41-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="26a41-121">Затем он использует префикс пространства имен для создания XML-литерала и доступа к первому дочернему узлу с полным именем `ns:phone` .</span><span class="sxs-lookup"><span data-stu-id="26a41-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="26a41-122">Затем он передает этот дочерний узел в `ShowName` подпрограммы, которая конструирует полное имя с помощью `GetXmlNamespace` оператора.</span><span class="sxs-lookup"><span data-stu-id="26a41-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="26a41-123">`ShowName`Затем подподпрограмма передает полное имя <xref:System.Xml.Linq.XNode.Ancestors%2A> методу, чтобы получить родительский `ns:contact` узел.</span><span class="sxs-lookup"><span data-stu-id="26a41-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="26a41-124">При вызове `TestGetXmlNamespace.RunSample()` отображается окно сообщения, содержащее следующий текст:</span><span class="sxs-lookup"><span data-stu-id="26a41-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="26a41-125">См. также</span><span class="sxs-lookup"><span data-stu-id="26a41-125">See also</span></span>

- [<span data-ttu-id="26a41-126">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="26a41-126">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="26a41-127">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26a41-127">Accessing XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/accessing-xml.md)
