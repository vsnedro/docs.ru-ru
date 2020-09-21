---
title: Инструмент определения схемы XML и сериализация XML
description: Средство определения схемы XML создает файлы классов C# или Visual Basic для схемы XSD и создает схему XML из библиотеки или исполняемого файла.
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: 6451f3b5f6e8ec2c1454e5cf7ffb95a96b620214
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554987"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Инструмент определения схемы XML и сериализация XML

Инструмент определения схемы XML ([XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) устанавливается вместе с инструментами .NET Framework в составе пакета средств разработки (SDK) Windows&reg;. Этот инструмент служит, главным образом, двум следующим целям.  
  
- Создание файлов классов C# или Visual Basic, соответствующих конкретной схеме языка определения схемы XML (XSD). Инструмент принимает схему XML как аргумент и создает файл с числом классов, которые при сериализации с использованием <xref:System.Xml.Serialization.XmlSerializer> соответствуют схеме. Дополнительные сведения об использовании этого инструмента для создания классов, которые соответствуют определенной схеме, см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](xml-schema-def-tool-gen.md).  
  
- Создание документа схемы XML из DLL-файла или EXE-файла. Чтобы просмотреть схему набора файлов, которая была создана или изменена с помощью атрибутов, передайте в инструмент файл DLL или EXE как аргумент для создания схемы XML. Сведения об использовании этого инструмента для создания документа схемы XML из набора классов см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](xml-schema-def-tool-gen.md).  
  
Дополнительные сведения об использовании этого инструмента см. в разделе [Инструмент определения схемы XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataSet>
- [Введение в сериализацию XML](introducing-xml-serialization.md)
- [Инструмент определения схемы XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Практическое руководство. Сериализация объекта](how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](how-to-deserialize-an-object.md)
- [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](xml-schema-def-tool-gen.md)
- [Поддержка привязки схемы XML](/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
