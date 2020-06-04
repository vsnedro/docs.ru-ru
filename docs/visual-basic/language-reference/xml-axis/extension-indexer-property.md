---
title: Свойство индексатора расширения
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: c91061d49e22e648b7bf75a812071b352793abcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401346"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="dba11-102">Свойство-индексатор расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dba11-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="dba11-103">Обеспечивает доступ к отдельным элементам коллекции.</span><span class="sxs-lookup"><span data-stu-id="dba11-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba11-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dba11-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="dba11-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="dba11-105">Parts</span></span>  
  
|<span data-ttu-id="dba11-106">Термин</span><span class="sxs-lookup"><span data-stu-id="dba11-106">Term</span></span>|<span data-ttu-id="dba11-107">Определение</span><span class="sxs-lookup"><span data-stu-id="dba11-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="dba11-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="dba11-108">Required.</span></span> <span data-ttu-id="dba11-109">Запрашиваемая коллекция.</span><span class="sxs-lookup"><span data-stu-id="dba11-109">A queryable collection.</span></span> <span data-ttu-id="dba11-110">То есть коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="dba11-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="dba11-111">(</span><span class="sxs-lookup"><span data-stu-id="dba11-111">(</span></span>|<span data-ttu-id="dba11-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="dba11-112">Required.</span></span> <span data-ttu-id="dba11-113">Обозначает начало свойства индексатора.</span><span class="sxs-lookup"><span data-stu-id="dba11-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="dba11-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="dba11-114">Required.</span></span> <span data-ttu-id="dba11-115">Целочисленное выражение, указывающее Отсчитываемая от нуля координату элемента коллекции.</span><span class="sxs-lookup"><span data-stu-id="dba11-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="dba11-116">)</span><span class="sxs-lookup"><span data-stu-id="dba11-116">)</span></span>|<span data-ttu-id="dba11-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="dba11-117">Required.</span></span> <span data-ttu-id="dba11-118">Обозначает конец свойства индексатора.</span><span class="sxs-lookup"><span data-stu-id="dba11-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="dba11-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dba11-119">Return Value</span></span>  
 <span data-ttu-id="dba11-120">Объект из указанного расположения в коллекции или значение, `Nothing` Если индекс выходит за пределы допустимого диапазона.</span><span class="sxs-lookup"><span data-stu-id="dba11-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dba11-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="dba11-121">Remarks</span></span>  
 <span data-ttu-id="dba11-122">Свойство индексатора расширения можно использовать для доступа к отдельным элементам в коллекции.</span><span class="sxs-lookup"><span data-stu-id="dba11-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="dba11-123">Это свойство индексатора обычно используется в выходных данных свойств оси XML.</span><span class="sxs-lookup"><span data-stu-id="dba11-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="dba11-124">Свойства дочерней оси XML и XML-потомков возвращают коллекции <xref:System.Xml.Linq.XElement> объектов или значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="dba11-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="dba11-125">Компилятор Visual Basic преобразует свойства индексатора расширения в вызовы `ElementAtOrDefault` метода.</span><span class="sxs-lookup"><span data-stu-id="dba11-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="dba11-126">В отличие от индексатора массива, `ElementAtOrDefault` метод возвращает значение, `Nothing` Если индекс выходит за пределы диапазона.</span><span class="sxs-lookup"><span data-stu-id="dba11-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="dba11-127">Такое поведение полезно в тех случаях, когда невозможно легко определить количество элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="dba11-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="dba11-128">Это свойство индексатора похоже на свойство расширения для коллекций, реализующих <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601> : оно используется только в том случае, если коллекция не имеет индексатора или свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dba11-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="dba11-129">Чтобы получить доступ к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XAttribute> объектов или, можно использовать `Value` свойство XML.</span><span class="sxs-lookup"><span data-stu-id="dba11-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="dba11-130">Дополнительные сведения см. в разделе [свойство значения XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="dba11-130">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dba11-131">Пример</span><span class="sxs-lookup"><span data-stu-id="dba11-131">Example</span></span>  
 <span data-ttu-id="dba11-132">В следующем примере показано, как использовать индексатор расширений для доступа ко второму дочернему узлу в коллекции <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="dba11-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="dba11-133">Доступ к коллекции осуществляется с помощью свойства дочерней оси, которое получает все дочерние элементы, указанные `phone` в `contact` объекте.</span><span class="sxs-lookup"><span data-stu-id="dba11-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="dba11-134">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="dba11-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="dba11-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dba11-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="dba11-136">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="dba11-136">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="dba11-137">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="dba11-137">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="dba11-138">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dba11-138">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="dba11-139">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="dba11-139">XML Value Property</span></span>](xml-value-property.md)
