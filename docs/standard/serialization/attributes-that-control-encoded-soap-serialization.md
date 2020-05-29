---
title: Атрибуты управления сериализацией с кодировкой SOAP
description: В этой статье приведен специальный набор атрибутов, найденных в пространстве имен System.Xml.Serialization, требуемый для обеспечения соответствия спецификации SOAP.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: 9e99856c3ac70b122c0def23e36bbc3059c5891c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378461"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="37c03-103">Атрибуты управления сериализацией с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="37c03-103">Attributes That Control Encoded SOAP Serialization</span></span>

<span data-ttu-id="37c03-104">В разделе номер 5 документа [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) описаны способы кодирования параметров SOAP.</span><span class="sxs-lookup"><span data-stu-id="37c03-104">The World Wide Web Consortium (W3C) document named [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="37c03-105">Для соответствия разделу 5 спецификации следует использовать специальный набор атрибутов, расположенный в пространстве имен <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="37c03-105">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="37c03-106">Примените эти атрибуты для соответствующих классов и членов классов, а затем используйте <xref:System.Xml.Serialization.XmlSerializer> для сериализации экземпляров класса или классов.</span><span class="sxs-lookup"><span data-stu-id="37c03-106">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>

<span data-ttu-id="37c03-107">В следующей таблице показаны атрибуты, место их применения и выполняемые ими действия.</span><span class="sxs-lookup"><span data-stu-id="37c03-107">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="37c03-108">Дополнительные сведения об использовании этих атрибутов для управления XML-сериализацией см. в статьях о том, как [ выполнить сериализацию объекта как потока XML с кодировкой SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) и [ переопределить сериализацию XML с кодировкой SOAP](how-to-override-encoded-soap-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="37c03-108">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](how-to-override-encoded-soap-xml-serialization.md).</span></span>

<span data-ttu-id="37c03-109">Дополнительные сведения об атрибутах см. в разделе [Атрибуты](../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="37c03-109">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span>

|<span data-ttu-id="37c03-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="37c03-110">Attribute</span></span>|<span data-ttu-id="37c03-111">Применение</span><span class="sxs-lookup"><span data-stu-id="37c03-111">Applies to</span></span>|<span data-ttu-id="37c03-112">Что определяет</span><span class="sxs-lookup"><span data-stu-id="37c03-112">Specifies</span></span>|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="37c03-113">Открытое поле, свойство, параметр или возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="37c03-113">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="37c03-114">Член класса должен быть сериализован как атрибут XML.</span><span class="sxs-lookup"><span data-stu-id="37c03-114">The class member will be serialized as an XML attribute.</span></span>|
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="37c03-115">Открытое поле, свойство, параметр или возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="37c03-115">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="37c03-116">Класс должен быть сериализован как элемент XML.</span><span class="sxs-lookup"><span data-stu-id="37c03-116">The class will be serialized as an XML element.</span></span>|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="37c03-117">Открытое поле, являющееся идентификатором перечисления.</span><span class="sxs-lookup"><span data-stu-id="37c03-117">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="37c03-118">Имя элемента члена перечисления.</span><span class="sxs-lookup"><span data-stu-id="37c03-118">The element name of an enumeration member.</span></span>|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="37c03-119">Открытые свойства и поля.</span><span class="sxs-lookup"><span data-stu-id="37c03-119">Public properties and fields.</span></span>|<span data-ttu-id="37c03-120">Свойство или поле должно игнорироваться при сериализации содержащего его класса.</span><span class="sxs-lookup"><span data-stu-id="37c03-120">The property or field should be ignored when the containing class is serialized.</span></span>|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="37c03-121">Объявления открытых производных классов и открытые методы для документов WSDL.</span><span class="sxs-lookup"><span data-stu-id="37c03-121">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="37c03-122">При создании схем должен быть включен тип (чтобы его можно было распознать во время сериализации).</span><span class="sxs-lookup"><span data-stu-id="37c03-122">The type should be included when generating schemas (to be recognized when serialized).</span></span>|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="37c03-123">Объявления открытых классов.</span><span class="sxs-lookup"><span data-stu-id="37c03-123">Public class declarations.</span></span>|<span data-ttu-id="37c03-124">Класс должен быть сериализован как тип XML.</span><span class="sxs-lookup"><span data-stu-id="37c03-124">The class should be serialized as an XML type.</span></span>|

## <a name="see-also"></a><span data-ttu-id="37c03-125">См. также</span><span class="sxs-lookup"><span data-stu-id="37c03-125">See also</span></span>

- [<span data-ttu-id="37c03-126">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="37c03-126">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="37c03-127">Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="37c03-127">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
- [<span data-ttu-id="37c03-128">Практическое руководство. Переопределение сериализации XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="37c03-128">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)
- [<span data-ttu-id="37c03-129">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="37c03-129">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="37c03-130">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="37c03-130">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="37c03-131">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="37c03-131">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
