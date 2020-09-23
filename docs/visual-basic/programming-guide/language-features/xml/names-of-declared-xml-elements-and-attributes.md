---
title: Имена объявленных элементов и атрибутов XML
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 2142674c3de4c5ac9e806c1328daa3efb697beb9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085624"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="3e7e0-102">Имена объявляемых элементов и атрибутов XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e7e0-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>

<span data-ttu-id="3e7e0-103">В этом разделе приводятся Visual Basic рекомендации по именованию XML-элементов и атрибутов в XML-литералах.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="3e7e0-104">В XML-литерале можно указать локальное имя или полное имя.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="3e7e0-105">Полное имя состоит из префикса пространства имен XML, двоеточия и локального имени.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="3e7e0-106">Дополнительные сведения о префиксах пространств имен XML см. в разделе [литерал XML-элемента](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="3e7e0-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3e7e0-107">Правила</span><span class="sxs-lookup"><span data-stu-id="3e7e0-107">Rules</span></span>  

 <span data-ttu-id="3e7e0-108">Локальное имя элемента или атрибута в Visual Basic должно соответствовать следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="3e7e0-109">Он может начинаться с пространства имен.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-109">It can begin with a namespace.</span></span> <span data-ttu-id="3e7e0-110">Оно должно начинаться с алфавитного символа или знака подчеркивания ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="3e7e0-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="3e7e0-111">Он должен содержать только алфавитные символы, десятичные цифры, символы подчеркивания, точки (.) и дефисы (-).</span><span class="sxs-lookup"><span data-stu-id="3e7e0-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="3e7e0-112">Длина не должна превышать 1 024 символов.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="3e7e0-113">Двоеточия, отображаемые в именах, указывают на пространство имен разделительной.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="3e7e0-114">Таким образом, можно использовать двоеточия только для указания пространства имен XML для определенного имени.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="3e7e0-115">Кроме того, следует следовать приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="3e7e0-116">Спецификация XML 1,0 резервирует все имена, начинающиеся с строки "XML", из любого варианта капитализации.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="3e7e0-117">Поэтому не используйте эти имена для элементов и имен атрибутов.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="3e7e0-118">Рекомендации по длине имени</span><span class="sxs-lookup"><span data-stu-id="3e7e0-118">Name Length Guidelines</span></span>  

 <span data-ttu-id="3e7e0-119">По сути, имя должно быть как можно более коротким, а также четко определять природу элемента.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="3e7e0-120">Это повышает удобочитаемость кода и сокращает длину строки и размер исходного файла.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="3e7e0-121">Однако ваше имя не должно быть настолько коротким, что оно не описывает элемент или его использование в коде.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="3e7e0-122">Это важно для удобочитаемости кода.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-122">This is important for the readability of your code.</span></span> <span data-ttu-id="3e7e0-123">Если кто-то другой пытается понять его, или если вы самостоятельно просматриваете его после написания, соответствующие имена элементов могут сэкономить время.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="3e7e0-124">Чувствительность к регистру в именах</span><span class="sxs-lookup"><span data-stu-id="3e7e0-124">Case Sensitivity in Names</span></span>  

 <span data-ttu-id="3e7e0-125">В именах XML-элементов учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-125">XML element names are case sensitive.</span></span> <span data-ttu-id="3e7e0-126">Это означает, что когда компилятор Visual Basic сравнивает два имени, отличающиеся только регистром букв, оно интерпретирует их как разные имена.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="3e7e0-127">Например, он интерпретирует `ABC` и `abc` ссылается на отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="3e7e0-128">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="3e7e0-128">XML Namespaces</span></span>  

 <span data-ttu-id="3e7e0-129">При создании литерала XML-элемента можно указать префикс пространства имен XML для имени элемента.</span><span class="sxs-lookup"><span data-stu-id="3e7e0-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="3e7e0-130">Дополнительные сведения см. в разделе [литерал XML-элемента](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="3e7e0-130">For more information, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7e0-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3e7e0-131">See also</span></span>

- [<span data-ttu-id="3e7e0-132">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3e7e0-132">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="3e7e0-133">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="3e7e0-133">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
