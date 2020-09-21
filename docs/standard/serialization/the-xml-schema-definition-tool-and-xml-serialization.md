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
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="910ce-103">Инструмент определения схемы XML и сериализация XML</span><span class="sxs-lookup"><span data-stu-id="910ce-103">The XML Schema Definition Tool and XML Serialization</span></span>

<span data-ttu-id="910ce-104">Инструмент определения схемы XML ([XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) устанавливается вместе с инструментами .NET Framework в составе пакета средств разработки (SDK) Windows&reg;.</span><span class="sxs-lookup"><span data-stu-id="910ce-104">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows&reg; Software Development Kit (SDK).</span></span> <span data-ttu-id="910ce-105">Этот инструмент служит, главным образом, двум следующим целям.</span><span class="sxs-lookup"><span data-stu-id="910ce-105">The tool is designed primarily for two purposes:</span></span>  
  
- <span data-ttu-id="910ce-106">Создание файлов классов C# или Visual Basic, соответствующих конкретной схеме языка определения схемы XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="910ce-106">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="910ce-107">Инструмент принимает схему XML как аргумент и создает файл с числом классов, которые при сериализации с использованием <xref:System.Xml.Serialization.XmlSerializer> соответствуют схеме.</span><span class="sxs-lookup"><span data-stu-id="910ce-107">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="910ce-108">Дополнительные сведения об использовании этого инструмента для создания классов, которые соответствуют определенной схеме, см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="910ce-108">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](xml-schema-def-tool-gen.md).</span></span>  
  
- <span data-ttu-id="910ce-109">Создание документа схемы XML из DLL-файла или EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="910ce-109">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="910ce-110">Чтобы просмотреть схему набора файлов, которая была создана или изменена с помощью атрибутов, передайте в инструмент файл DLL или EXE как аргумент для создания схемы XML.</span><span class="sxs-lookup"><span data-stu-id="910ce-110">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="910ce-111">Сведения об использовании этого инструмента для создания документа схемы XML из набора классов см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="910ce-111">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](xml-schema-def-tool-gen.md).</span></span>  
  
<span data-ttu-id="910ce-112">Дополнительные сведения об использовании этого инструмента см. в разделе [Инструмент определения схемы XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="910ce-112">For more information about using the tool, see [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910ce-113">См. также</span><span class="sxs-lookup"><span data-stu-id="910ce-113">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="910ce-114">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="910ce-114">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="910ce-115">Инструмент определения схемы XML (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="910ce-115">XML Schema Definition Tool (Xsd.exe)</span></span>](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="910ce-116">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="910ce-116">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="910ce-117">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="910ce-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- [<span data-ttu-id="910ce-118">Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML</span><span class="sxs-lookup"><span data-stu-id="910ce-118">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](xml-schema-def-tool-gen.md)
- <span data-ttu-id="910ce-119">[Поддержка привязки схемы XML](/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="910ce-119">[XML Schema Binding Support](/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span></span>
