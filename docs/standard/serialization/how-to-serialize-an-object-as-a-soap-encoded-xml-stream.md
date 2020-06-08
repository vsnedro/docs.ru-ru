---
title: Практическое руководство. Как сериализовать объект как поток XML с кодировкой SOAP
description: Узнайте, как сериализовать объект как поток XML с кодировкой SOAP. Класс XmlSerializer можно использовать для сериализации классов и создания закодированных сообщений SOAP.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: 1d38c4e334439ef41b4d4429e52cff04c6463573
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84291569"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="e2d14-104">Практическое руководство. Как сериализовать объект как поток XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="e2d14-104">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="e2d14-105">Поскольку сообщение SOAP сформировано с использованием XML, можно использовать <xref:System.Xml.Serialization.XmlSerializer> для сериализации классов и генерации сообщений с кодировкой SOAP.</span><span class="sxs-lookup"><span data-stu-id="e2d14-105">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="e2d14-106">Полученный в результате код XML соответствует [разделу 5 документа "Simple Object Access Protocol (SOAP) 1.1", разработанного консорциумом W3С](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="e2d14-106">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="e2d14-107">При создании XML-веб-службы, которая осуществляет связь посредством сообщений SOAP, можно настроить поток XML, применив к классам и членам классов набор специальных атрибутов SOAP.</span><span class="sxs-lookup"><span data-stu-id="e2d14-107">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="e2d14-108">Список атрибутов см. в разделе [Атрибуты, которые управляют сериализацией с кодировкой SOAP](attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="e2d14-108">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="e2d14-109">Чтобы сериализовать объект как поток XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="e2d14-109">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1. <span data-ttu-id="e2d14-110">Создайте класс с помощью [средства определения схемы XML (xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e2d14-110">Create the class using the [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2. <span data-ttu-id="e2d14-111">Примените один или несколько специальных атрибутов из `System.Xml.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="e2d14-111">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="e2d14-112">Список атрибутов см. в разделе "Атрибуты управления сериализацией с кодировкой SOAP".</span><span class="sxs-lookup"><span data-stu-id="e2d14-112">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3. <span data-ttu-id="e2d14-113">Создайте `XmlTypeMapping` путем создания нового `SoapReflectionImporter` и вызова метода `ImportTypeMapping` с типом сериализуемого класса.</span><span class="sxs-lookup"><span data-stu-id="e2d14-113">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="e2d14-114">В следующем примере кода вызывается метод `ImportTypeMapping` класса `SoapReflectionImporter` для создания `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="e2d14-114">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4. <span data-ttu-id="e2d14-115">Создайте экземпляр класса `XmlSerializer`, передав `XmlTypeMapping` конструктору <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.</span><span class="sxs-lookup"><span data-stu-id="e2d14-115">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. <span data-ttu-id="e2d14-116">Вызовите метод `Serialize` или `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="e2d14-116">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2d14-117">Пример</span><span class="sxs-lookup"><span data-stu-id="e2d14-117">Example</span></span>  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2d14-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e2d14-118">See also</span></span>

- [<span data-ttu-id="e2d14-119">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="e2d14-119">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="e2d14-120">Атрибуты управления сериализацией с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="e2d14-120">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="e2d14-121">Сериализация XML с использованием XML-веб-служб</span><span class="sxs-lookup"><span data-stu-id="e2d14-121">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)
- [<span data-ttu-id="e2d14-122">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="e2d14-122">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="e2d14-123">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="e2d14-123">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- [<span data-ttu-id="e2d14-124">Практическое руководство. Переопределение сериализации XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="e2d14-124">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)
