---
title: Чтение данных объекта из XML-файла (C#)
description: В этом примере C# демонстрируется считывание данных объекта, которые ранее были записаны в XML-файл с помощью класса XmlSerializer.
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 525a93812279756b3802d43d85bb5e61d8f7415e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302793"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="bed5d-103">Чтение данных объекта из XML-файла (C#)</span><span class="sxs-lookup"><span data-stu-id="bed5d-103">How to read object data from an XML file (C#)</span></span>
<span data-ttu-id="bed5d-104">В этом примере демонстрируется считывание данных объекта, которые ранее были записаны в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bed5d-104">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed5d-105">Пример</span><span class="sxs-lookup"><span data-stu-id="bed5d-105">Example</span></span>  
  
```csharp  
public class Book  
{  
    public String title;  
}
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bed5d-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bed5d-106">Compiling the Code</span></span>  
<span data-ttu-id="bed5d-107">Замените имя файла "c:\temp\SerializationOverview.xml" на имя файла, в котором содержатся сериализованные данные.</span><span class="sxs-lookup"><span data-stu-id="bed5d-107">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="bed5d-108">Дополнительные сведения о сериализации данных см. в руководстве по [записи данных объекта в XML-файл (C#)](./how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="bed5d-108">For more information about serializing data, see [How to write object data to an XML file (C#)](./how-to-write-object-data-to-an-xml-file.md).</span></span>
  
 <span data-ttu-id="bed5d-109">У класса должен быть открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="bed5d-109">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="bed5d-110">Десериализуются только открытые свойства и поля.</span><span class="sxs-lookup"><span data-stu-id="bed5d-110">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bed5d-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="bed5d-111">Robust Programming</span></span>  
 <span data-ttu-id="bed5d-112">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="bed5d-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="bed5d-113">В сериализуемом классе нет открытого конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="bed5d-113">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="bed5d-114">Данные в файле не являются данными из класса, который десериализуется.</span><span class="sxs-lookup"><span data-stu-id="bed5d-114">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="bed5d-115">Файл не существует (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="bed5d-115">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="bed5d-116">Безопасность .NET</span><span class="sxs-lookup"><span data-stu-id="bed5d-116">.NET Security</span></span>  
 <span data-ttu-id="bed5d-117">Всегда проверяйте входные данные и никогда не десериализуйте данные из непроверенных источников.</span><span class="sxs-lookup"><span data-stu-id="bed5d-117">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="bed5d-118">Созданный заново объект выполняется на локальном компьютере с разрешениями кода, который его десериализовал.</span><span class="sxs-lookup"><span data-stu-id="bed5d-118">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="bed5d-119">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="bed5d-119">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed5d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="bed5d-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="bed5d-121">Практическое руководство. Запись данных объекта в XML-файл (C#)</span><span class="sxs-lookup"><span data-stu-id="bed5d-121">How to write object data to an XML file (C#)</span></span>](./how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="bed5d-122">Сериализация (C#)</span><span class="sxs-lookup"><span data-stu-id="bed5d-122">Serialization (C#)</span></span>](./index.md)
- [<span data-ttu-id="bed5d-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bed5d-123">C# Programming Guide</span></span>](../../index.md)
