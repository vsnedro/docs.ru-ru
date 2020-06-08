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
ms.openlocfilehash: c88770403d4c2abfb5ce99f44ea1bec1f8337545
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84279780"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="b596e-103">Инструмент определения схемы XML и сериализация XML</span><span class="sxs-lookup"><span data-stu-id="b596e-103">The XML Schema Definition Tool and XML Serialization</span></span>

<span data-ttu-id="b596e-104">Инструмент определения схемы XML ([XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) устанавливается вместе с инструментами .NET Framework в составе пакета средств разработки (SDK) Windows&reg;.</span><span class="sxs-lookup"><span data-stu-id="b596e-104">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows&reg; Software Development Kit (SDK).</span></span> <span data-ttu-id="b596e-105">Этот инструмент служит, главным образом, двум следующим целям.</span><span class="sxs-lookup"><span data-stu-id="b596e-105">The tool is designed primarily for two purposes:</span></span>  
  
- <span data-ttu-id="b596e-106">Создание файлов классов C# или Visual Basic, соответствующих конкретной схеме языка определения схемы XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="b596e-106">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="b596e-107">Инструмент принимает схему XML как аргумент и создает файл с числом классов, которые при сериализации с использованием <xref:System.Xml.Serialization.XmlSerializer> соответствуют схеме.</span><span class="sxs-lookup"><span data-stu-id="b596e-107">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="b596e-108">Дополнительные сведения об использовании этого инструмента для создания классов, которые соответствуют определенной схеме, см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="b596e-108">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](xml-schema-def-tool-gen.md).</span></span>  
  
- <span data-ttu-id="b596e-109">Создание документа схемы XML из DLL-файла или EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="b596e-109">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="b596e-110">Чтобы просмотреть схему набора файлов, которая была создана или изменена с помощью атрибутов, передайте в инструмент файл DLL или EXE как аргумент для создания схемы XML.</span><span class="sxs-lookup"><span data-stu-id="b596e-110">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="b596e-111">Сведения об использовании этого инструмента для создания документа схемы XML из набора классов см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="b596e-111">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](xml-schema-def-tool-gen.md).</span></span>  
  
<span data-ttu-id="b596e-112">Дополнительные сведения об использовании этого инструмента см. в разделе [Инструмент определения схемы XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b596e-112">For more information about using the tool, see [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b596e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b596e-113">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="b596e-114">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="b596e-114">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="b596e-115">Инструмент определения схемы XML (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="b596e-115">XML Schema Definition Tool (Xsd.exe)</span></span>](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="b596e-116">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="b596e-116">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="b596e-117">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="b596e-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- [<span data-ttu-id="b596e-118">Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML</span><span class="sxs-lookup"><span data-stu-id="b596e-118">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](xml-schema-def-tool-gen.md)
- <span data-ttu-id="b596e-119">[Поддержка привязки схемы XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b596e-119">[XML Schema Binding Support](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span></span>
