---
title: Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML
description: Узнайте, как использовать средство определения схемы XML для создания схемы XML, которая описывает класс, или для создания класса, определенного схемой XML.
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 9d94ed7c2558b1d60efb8b3cdbaac1ea1f0087b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676664"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML

С помощью инструмента определения схемы XML (Xsd.exe) можно создать схему XML, которая описывает класс, или создать класс, определенный схемой XML. В процедурах ниже показана методика выполнения таких операций.

Инструмент определения схемы XML (Xsd.exe) обычно можно найти по следующему пути:\
_C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\{версия}\\bin\\NETFX {версия} Tools\\_

### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>Создание классов, соответствующих определенной схеме  
  
1. Откройте окно командной строки.  
  
2. Передайте схему XML как аргумент в инструмент определения схемы XML, который создаст набор классов, точно соответствующих схеме XML, например:  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     Средство может обрабатывать только схемы, которые ссылаются на спецификацию XML консорциума W3C от 16 марта 2001 г. Иными словами, пространство имен схемы XML должно иметь вид "http://www.w3.org/2001/XMLSchema", как показано в следующем примере.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. При необходимости измените классы с методами, свойствами или полями. Дополнительные сведения об изменении класса с помощью атрибутов см. в разделах [Управление сериализацией XML с использованием атрибутов](controlling-xml-serialization-using-attributes.md) и [Атрибуты управления сериализацией с кодировкой SOAP](attributes-that-control-encoded-soap-serialization.md).  
  
 Часто бывает полезным изучить схему потока XML, которая генерируется при сериализации экземпляров класса (или классов). Например, можно опубликовать схему для совместного использования или сравнить ее со схемой, в которой предпринимается попытка обеспечения соответствия.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>Создание документа схемы XML из набора классов  
  
1. Скомпилируйте класс или классы в библиотеку DLL.  
  
2. Откройте окно командной строки.  
  
3. Передайте библиотеку DLL как аргумент в Xsd.exe, например:  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     В результате записывается схема (или схемы), которая начинается с имени "schema0.xsd".  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataSet>
- [Инструмент определения схемы XML и сериализация XML](the-xml-schema-definition-tool-and-xml-serialization.md)
- [Введение в сериализацию XML](introducing-xml-serialization.md)
- [Инструмент определения схемы XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Практическое руководство. Сериализация объекта](how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](how-to-deserialize-an-object.md)
