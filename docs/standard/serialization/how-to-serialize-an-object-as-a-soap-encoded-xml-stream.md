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
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Практическое руководство. Как сериализовать объект как поток XML с кодировкой SOAP
  
 Поскольку сообщение SOAP сформировано с использованием XML, можно использовать <xref:System.Xml.Serialization.XmlSerializer> для сериализации классов и генерации сообщений с кодировкой SOAP. Полученный в результате код XML соответствует [разделу 5 документа "Simple Object Access Protocol (SOAP) 1.1", разработанного консорциумом W3С](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512). При создании XML-веб-службы, которая осуществляет связь посредством сообщений SOAP, можно настроить поток XML, применив к классам и членам классов набор специальных атрибутов SOAP. Список атрибутов см. в разделе [Атрибуты, которые управляют сериализацией с кодировкой SOAP](attributes-that-control-encoded-soap-serialization.md).  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Чтобы сериализовать объект как поток XML с кодировкой SOAP  
  
1. Создайте класс с помощью [средства определения схемы XML (xsd.exe)](xml-schema-definition-tool-xsd-exe.md).  
  
2. Примените один или несколько специальных атрибутов из `System.Xml.Serialization`. Список атрибутов см. в разделе "Атрибуты управления сериализацией с кодировкой SOAP".  
  
3. Создайте `XmlTypeMapping` путем создания нового `SoapReflectionImporter` и вызова метода `ImportTypeMapping` с типом сериализуемого класса.  
  
     В следующем примере кода вызывается метод `ImportTypeMapping` класса `SoapReflectionImporter` для создания `XmlTypeMapping`.  
  
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
  
4. Создайте экземпляр класса `XmlSerializer`, передав `XmlTypeMapping` конструктору <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. Вызовите метод `Serialize` или `Deserialize`.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также

- [Сериализация XML и SOAP](xml-and-soap-serialization.md)
- [Атрибуты управления сериализацией с кодировкой SOAP](attributes-that-control-encoded-soap-serialization.md)
- [Сериализация XML с использованием XML-веб-служб](xml-serialization-with-xml-web-services.md)
- [Практическое руководство. Сериализация объекта](how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](how-to-deserialize-an-object.md)
- [Практическое руководство. Переопределение сериализации XML с кодировкой SOAP](how-to-override-encoded-soap-xml-serialization.md)
