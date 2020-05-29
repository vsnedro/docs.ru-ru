---
title: Практическое руководство. Указание имени альтернативного элемента для потока XML
description: Узнайте, как создать поток XML с альтернативным именем элемента, например, для веб-служб XML, которым требуются одни и те же данные с незначительными различиями.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
ms.openlocfilehash: d9851226b602226e00648d8742bf0a49c902c33b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377393"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a><span data-ttu-id="3fbb6-103">Практическое руководство. Указание имени альтернативного элемента для потока XML</span><span class="sxs-lookup"><span data-stu-id="3fbb6-103">How to: Specify an Alternate Element Name for an XML Stream</span></span>
  
<span data-ttu-id="3fbb6-104">Используя <xref:System.Xml.Serialization.XmlSerializer>, можно создать несколько потоков XML с одним и тем же набором классов.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-104">Using the <xref:System.Xml.Serialization.XmlSerializer>, you can generate more than one XML stream with the same set of classes.</span></span> <span data-ttu-id="3fbb6-105">Это может понадобиться, поскольку для двух разных XML-веб-служб требуется одинаковая основная информация с незначительными различиями.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-105">You might want to do this because two different XML Web services require the same basic information, with only slight differences.</span></span> <span data-ttu-id="3fbb6-106">Допустим, две веб-службы XML обрабатывают заказы на книги, и поэтому для каждой из них требуются номера ISBN.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-106">For example, imagine two XML Web services that process orders for books, and thus both require ISBN numbers.</span></span> <span data-ttu-id="3fbb6-107">Одна служба использует тег \<ISBN>, а другая — тег \<BookID>.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-107">One service uses the tag \<ISBN> while the second uses the tag \<BookID>.</span></span> <span data-ttu-id="3fbb6-108">Имеется класс с именем `Book`, содержащий поле с именем `ISBN`.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-108">You have a class named `Book` that contains a field named `ISBN`.</span></span> <span data-ttu-id="3fbb6-109">При сериализации экземпляра класса `Book` имя члена (ISBN) будет по умолчанию использоваться в качестве имени элемента для тега.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-109">When an instance of the `Book` class is serialized, it will, by default, use the member name (ISBN) as the tag element name.</span></span> <span data-ttu-id="3fbb6-110">Первая XML-веб-служба работает, как и предполагалось.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-110">For the first XML Web service, this is as expected.</span></span> <span data-ttu-id="3fbb6-111">Но чтобы отправить поток XML во вторую XML-веб-службу, необходимо переопределить сериализацию, чтобы именем элемента для тега стало `BookID`.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-111">But to send the XML stream to the second XML Web service, you must override the serialization so that the tag's element name is `BookID`.</span></span>  
  
## <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a><span data-ttu-id="3fbb6-112">Создание потока XML с именем альтернативного элемента</span><span class="sxs-lookup"><span data-stu-id="3fbb6-112">To create an XML stream with an alternate element name</span></span>  
  
1. <span data-ttu-id="3fbb6-113">Создайте экземпляр класса <xref:System.Xml.Serialization.XmlElementAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-113">Create an instance of the <xref:System.Xml.Serialization.XmlElementAttribute> class.</span></span>  
  
2. <span data-ttu-id="3fbb6-114">Задайте <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> атрибута <xref:System.Xml.Serialization.XmlElementAttribute> как "BookID".</span><span class="sxs-lookup"><span data-stu-id="3fbb6-114">Set the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> of the <xref:System.Xml.Serialization.XmlElementAttribute> to "BookID".</span></span>  
  
3. <span data-ttu-id="3fbb6-115">Создайте экземпляр класса <xref:System.Xml.Serialization.XmlAttributes>.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-115">Create an instance of the <xref:System.Xml.Serialization.XmlAttributes> class.</span></span>  
  
4. <span data-ttu-id="3fbb6-116">Добавьте объект `XmlElementAttribute` в коллекцию, доступ к которой осуществляется через свойство <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> атрибута <xref:System.Xml.Serialization.XmlAttributes>.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-116">Add the `XmlElementAttribute` object to the collection accessed through the <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> property of <xref:System.Xml.Serialization.XmlAttributes> .</span></span>  
  
5. <span data-ttu-id="3fbb6-117">Создайте экземпляр класса <xref:System.Xml.Serialization.XmlAttributeOverrides>.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-117">Create an instance of the <xref:System.Xml.Serialization.XmlAttributeOverrides> class.</span></span>  
  
6. <span data-ttu-id="3fbb6-118">Добавьте `XmlAttributes` к <xref:System.Xml.Serialization.XmlAttributeOverrides>, передавая тип переопределяемого объекта и имя переопределяемого члена.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-118">Add the `XmlAttributes` to the <xref:System.Xml.Serialization.XmlAttributeOverrides>, passing the type of the object to override and the name of the member being overridden.</span></span>  
  
7. <span data-ttu-id="3fbb6-119">Создайте экземпляр класса `XmlSerializer` с `XmlAttributeOverrides`.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-119">Create an instance of the `XmlSerializer` class with `XmlAttributeOverrides`.</span></span>  
  
8. <span data-ttu-id="3fbb6-120">Создайте экземпляр класса `Book`, сериализуйте или десериализуйте его.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-120">Create an instance of the `Book` class, and serialize or deserialize it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fbb6-121">Пример</span><span class="sxs-lookup"><span data-stu-id="3fbb6-121">Example</span></span>  
  
```vb  
Public Function SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
```  
  
```csharp  
public void SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 <span data-ttu-id="3fbb6-122">Поток XML может иметь следующий вид.</span><span class="sxs-lookup"><span data-stu-id="3fbb6-122">The XML stream might resemble the following.</span></span>  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fbb6-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3fbb6-123">See also</span></span>

- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [<span data-ttu-id="3fbb6-124">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="3fbb6-124">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="3fbb6-125">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="3fbb6-125">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="3fbb6-126">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="3fbb6-126">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
