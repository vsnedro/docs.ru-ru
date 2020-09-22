---
title: XML-литерал CDATA
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 4447ad6cf0fb251b0d2d1387c109b06d32f69cb8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866101"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="981fd-102">Литеральное представление XML-раздела CDATA (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="981fd-102">XML CDATA Literal (Visual Basic)</span></span>

<span data-ttu-id="981fd-103">Литерал, представляющий <xref:System.Xml.Linq.XCData> объект.</span><span class="sxs-lookup"><span data-stu-id="981fd-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="981fd-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="981fd-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="981fd-105">Parts</span></span>  

 `<![CDATA[`  
 <span data-ttu-id="981fd-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="981fd-106">Required.</span></span> <span data-ttu-id="981fd-107">Обозначает начало раздела XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="981fd-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="981fd-108">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="981fd-108">Required.</span></span> <span data-ttu-id="981fd-109">Текстовое содержимое, отображаемое в разделе CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="981fd-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="981fd-110">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="981fd-110">Required.</span></span> <span data-ttu-id="981fd-111">Обозначает конец раздела.</span><span class="sxs-lookup"><span data-stu-id="981fd-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="981fd-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="981fd-112">Return Value</span></span>  

 <span data-ttu-id="981fd-113">Объект <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="981fd-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="981fd-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="981fd-114">Remarks</span></span>  

 <span data-ttu-id="981fd-115">Разделы XML CDATA содержат необработанный текст, который должен быть добавлен, но не проанализирован, с XML-кодом, содержащим его.</span><span class="sxs-lookup"><span data-stu-id="981fd-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="981fd-116">Раздел CDATA XML может содержать любой текст.</span><span class="sxs-lookup"><span data-stu-id="981fd-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="981fd-117">Сюда входят зарезервированные символы XML.</span><span class="sxs-lookup"><span data-stu-id="981fd-117">This includes reserved XML characters.</span></span> <span data-ttu-id="981fd-118">Раздел CDATA XML заканчивается последовательностью "]] >".</span><span class="sxs-lookup"><span data-stu-id="981fd-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="981fd-119">Это подразумевает следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="981fd-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="981fd-120">Нельзя использовать внедренное выражение в XML-литерале CDATA, так как разделители внедренных выражений являются допустимыми содержимым XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="981fd-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="981fd-121">Разделы CDATA XML не могут быть вложенными, поскольку `content` не могут содержать значение "]] >".</span><span class="sxs-lookup"><span data-stu-id="981fd-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="981fd-122">Можно назначить литерал XML CDATA переменной или включить его в литерал XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="981fd-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="981fd-123">XML-литерал может охватывать несколько строк, но не использует символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="981fd-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="981fd-124">Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.</span><span class="sxs-lookup"><span data-stu-id="981fd-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="981fd-125">Компилятор Visual Basic преобразует литерал CDATA XML в вызов <xref:System.Xml.Linq.XCData.%23ctor%2A> конструктора.</span><span class="sxs-lookup"><span data-stu-id="981fd-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="981fd-126">Пример</span><span class="sxs-lookup"><span data-stu-id="981fd-126">Example</span></span>  

 <span data-ttu-id="981fd-127">В следующем примере создается раздел CDATA, содержащий текст "может содержать литеральные \<XML> теги".</span><span class="sxs-lookup"><span data-stu-id="981fd-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="981fd-128">См. также</span><span class="sxs-lookup"><span data-stu-id="981fd-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="981fd-129">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="981fd-129">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="981fd-130">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="981fd-130">XML Literals</span></span>](index.md)
- [<span data-ttu-id="981fd-131">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="981fd-131">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
