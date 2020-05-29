---
title: Базовая сериализация
description: В этой статье описано, как сделать класс сериализуемым с помощью атрибута SerializableAttribute, и показаны примеры сериализации и десериализации.
ms.date: 03/30/2017
helpviewer_keywords:
- binary serialization, basic serialization
- serialization, basic serialization
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
dev_langs:
- CSharp
ms.openlocfilehash: 98ea6f23467b85dc270aa323e72a8a9b0934994a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378429"
---
# <a name="basic-serialization"></a><span data-ttu-id="ffebd-103">Базовая сериализация</span><span class="sxs-lookup"><span data-stu-id="ffebd-103">Basic serialization</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="ffebd-104">Самый простой способ создать сериализуемый класс — отметить его атрибутом <xref:System.SerializableAttribute> следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ffebd-104">The easiest way to make a class serializable is to mark it with the <xref:System.SerializableAttribute> as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
<span data-ttu-id="ffebd-105">В следующем примере кода показано, как экземпляр этого класса можно сериализовать в файл.</span><span class="sxs-lookup"><span data-stu-id="ffebd-105">The following code example shows how an instance of this class can be serialized to a file.</span></span>  
  
```csharp  
MyObject obj = new MyObject();  
obj.n1 = 1;  
obj.n2 = 24;  
obj.str = "Some String";  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Create, FileAccess.Write, FileShare.None);  
formatter.Serialize(stream, obj);  
stream.Close();  
```  
  
<span data-ttu-id="ffebd-106">В этом примере для сериализации используется двоичный модуль форматирования.</span><span class="sxs-lookup"><span data-stu-id="ffebd-106">This example uses a binary formatter to do the serialization.</span></span> <span data-ttu-id="ffebd-107">Все, что нужно сделать, — создать экземпляр потока и модуль форматирования, который будет использоваться, а затем вызвать для модуля форматирования метод **Serialize**.</span><span class="sxs-lookup"><span data-stu-id="ffebd-107">All you need to do is create an instance of the stream and the formatter you intend to use, and then call the **Serialize** method on the formatter.</span></span> <span data-ttu-id="ffebd-108">Сериализуемый поток и объект для этого вызова предоставляются как параметры.</span><span class="sxs-lookup"><span data-stu-id="ffebd-108">The stream and the object to serialize are provided as parameters to this call.</span></span> <span data-ttu-id="ffebd-109">Хотя в этом примере это явно не показано, будут сериализованы все переменные членов класса - даже переменные, отмеченные как закрытые.</span><span class="sxs-lookup"><span data-stu-id="ffebd-109">Although it is not explicitly demonstrated in this example, all member variables of a class will be serialized—even variables marked as private.</span></span> <span data-ttu-id="ffebd-110">Таким образом, двоичная сериализация отличается от класса <xref:System.Xml.Serialization.XmlSerializer>, при котором выполняется сериализация только открытых полей.</span><span class="sxs-lookup"><span data-stu-id="ffebd-110">In this aspect, binary serialization differs from the <xref:System.Xml.Serialization.XmlSerializer> class, which only serializes public fields.</span></span> <span data-ttu-id="ffebd-111">Сведения об исключении переменных членов из двоичной сериализации см. в разделе [Выборочная сериализация](selective-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="ffebd-111">For information on excluding member variables from binary serialization, see [Selective Serialization](selective-serialization.md).</span></span>  
  
<span data-ttu-id="ffebd-112">Не менее просто и восстановление объекта в предыдущее состояние.</span><span class="sxs-lookup"><span data-stu-id="ffebd-112">Restoring the object back to its former state is just as easy.</span></span> <span data-ttu-id="ffebd-113">Сначала создайте поток для чтения и <xref:System.Runtime.Serialization.Formatter>, а затем дайте модулю форматирования команду десериализовать объект.</span><span class="sxs-lookup"><span data-stu-id="ffebd-113">First, create a stream for reading and a <xref:System.Runtime.Serialization.Formatter>, and then instruct the formatter to deserialize the object.</span></span> <span data-ttu-id="ffebd-114">Эта процедура показана в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ffebd-114">The code example below shows how this is done.</span></span>  
  
```csharp  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Open, FileAccess.Read, FileShare.Read);  
MyObject obj = (MyObject) formatter.Deserialize(stream);  
stream.Close();  
  
// Here's the proof.  
Console.WriteLine("n1: {0}", obj.n1);  
Console.WriteLine("n2: {0}", obj.n2);  
Console.WriteLine("str: {0}", obj.str);  
```  
  
<span data-ttu-id="ffebd-115">Используемый выше <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> очень эффективен и генерирует компактный поток байтов.</span><span class="sxs-lookup"><span data-stu-id="ffebd-115">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> used above is very efficient and produces a compact byte stream.</span></span> <span data-ttu-id="ffebd-116">Все сериализуемые с использованием этого модуля форматирования объекты можно также десериализовать с его помощью, что делает его идеальным инструментом для сериализации объектов, которые будут десериализованы в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ffebd-116">All objects serialized with this formatter can also be deserialized with it, which makes it an ideal tool for serializing objects that will be deserialized on the .NET Framework.</span></span> <span data-ttu-id="ffebd-117">Важно отметить, что во время десериализации объекта конструкторы не вызываются.</span><span class="sxs-lookup"><span data-stu-id="ffebd-117">It is important to note that constructors are not called when an object is deserialized.</span></span> <span data-ttu-id="ffebd-118">Это ограничение накладывается на десериализацию по причинам обеспечения производительности.</span><span class="sxs-lookup"><span data-stu-id="ffebd-118">This constraint is placed on deserialization for performance reasons.</span></span> <span data-ttu-id="ffebd-119">Однако при этом способе нарушаются некоторые обычные контракты, которые осуществляет среда выполнения с использованием модуля записи объектов, и разработчики, отмечая объект как сериализуемый, должны понимать последствия.</span><span class="sxs-lookup"><span data-stu-id="ffebd-119">However, this violates some of the usual contracts the runtime makes with the object writer, and developers should ensure that they understand the ramifications when marking an object as serializable.</span></span>  
  
<span data-ttu-id="ffebd-120">Если требуется обеспечение переносимости, используйте <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span><span class="sxs-lookup"><span data-stu-id="ffebd-120">If portability is a requirement, use the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> instead.</span></span> <span data-ttu-id="ffebd-121">Просто замените **BinaryFormatter** в коде выше на **SoapFormatter** и вызовите **Serialize** и **Deserialize**, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="ffebd-121">Simply replace the **BinaryFormatter** in the code above with **SoapFormatter,** and call **Serialize** and **Deserialize** as before.</span></span> <span data-ttu-id="ffebd-122">Результатом работы этого модуля форматирования в примере выше является следующее.</span><span class="sxs-lookup"><span data-stu-id="ffebd-122">This formatter produces the following output for the example used above.</span></span>  
  
```xml  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:a1="http://schemas.microsoft.com/clr/assem/ToFile">  
  
  <SOAP-ENV:Body>  
    <a1:MyObject id="ref-1">  
      <n1>1</n1>  
      <n2>24</n2>  
      <str id="ref-3">Some String</str>  
    </a1:MyObject>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>  
```  
  
<span data-ttu-id="ffebd-123">Важно отметить, что атрибут [Serializable](xref:System.SerializableAttribute) не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="ffebd-123">It's important to note that the [Serializable](xref:System.SerializableAttribute) attribute cannot be inherited.</span></span> <span data-ttu-id="ffebd-124">Если новый класс наследуется от `MyObject`, новый класс также должен быть отмечен атрибутом, иначе его сериализация невозможна.</span><span class="sxs-lookup"><span data-stu-id="ffebd-124">If you derive a new class from `MyObject`, the new class must be marked with the attribute as well, or it cannot be serialized.</span></span> <span data-ttu-id="ffebd-125">Например, при попытке сериализовать экземпляр класса (см. ниже) будет выдано исключение <xref:System.Runtime.Serialization.SerializationException>, информирующее о том, что тип `MyStuff` не отмечен как сериализуемый.</span><span class="sxs-lookup"><span data-stu-id="ffebd-125">For example, when you attempt to serialize an instance of the class below, you'll get a <xref:System.Runtime.Serialization.SerializationException> informing you that the `MyStuff` type is not marked as serializable.</span></span>  
  
```csharp  
public class MyStuff : MyObject
{  
  public int n3;  
}  
```  
  
 <span data-ttu-id="ffebd-126">Использование атрибута [Serializable](xref:System.SerializableAttribute) удобно, но у него есть свои ограничения, как это показано выше.</span><span class="sxs-lookup"><span data-stu-id="ffebd-126">Using the [Serializable](xref:System.SerializableAttribute) attribute is convenient, but it has limitations as previously demonstrated.</span></span> <span data-ttu-id="ffebd-127">См. раздел [Правила сериализации](serialization-guidelines.md), чтобы получить сведения о том, в каких случаях класс следует отмечать для сериализации.</span><span class="sxs-lookup"><span data-stu-id="ffebd-127">Refer to the [Serialization Guidelines](serialization-guidelines.md) for information about when you should mark a class for serialization.</span></span> <span data-ttu-id="ffebd-128">Сериализацию невозможно добавить в класс после его компиляции.</span><span class="sxs-lookup"><span data-stu-id="ffebd-128">Serialization cannot be added to a class after it has been compiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffebd-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ffebd-129">See also</span></span>

- [<span data-ttu-id="ffebd-130">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="ffebd-130">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="ffebd-131">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="ffebd-131">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
