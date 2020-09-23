---
title: Практическое руководство. Запись данных объекта в XML-файл
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: af62d10b29e76701668fd3d595b967bd1754a22c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077232"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="1f9d6-102">How to: Write Object Data to an XML File (Visual Basic) (Практическое руководство. Запись данных объекта в XML-файл (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="1f9d6-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>

<span data-ttu-id="1f9d6-103">Показывает, как записать объект из класса в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1f9d6-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f9d6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1f9d6-104">Example</span></span>  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compile-the-code"></a><span data-ttu-id="1f9d6-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1f9d6-105">Compile the code</span></span>  

 <span data-ttu-id="1f9d6-106">У класса должен быть открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="1f9d6-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1f9d6-107">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="1f9d6-107">Robust Programming</span></span>  

 <span data-ttu-id="1f9d6-108">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="1f9d6-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="1f9d6-109">В сериализуемом классе нет открытого конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="1f9d6-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="1f9d6-110">Файл существует и является файлом только для чтения (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="1f9d6-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="1f9d6-111">Слишком длинный путь (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="1f9d6-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="1f9d6-112">Диск заполнен (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="1f9d6-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1f9d6-113">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1f9d6-113">.NET Framework Security</span></span>  

 <span data-ttu-id="1f9d6-114">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="1f9d6-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="1f9d6-115">Если приложению требуется создать файл, оно должно иметь доступ к каталогу для создания файлов (`Create`).</span><span class="sxs-lookup"><span data-stu-id="1f9d6-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="1f9d6-116">Если файл уже существует, то приложению достаточно иметь лишь доступ для записи файлов (`Write`), т. е. меньшие привилегии.</span><span class="sxs-lookup"><span data-stu-id="1f9d6-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="1f9d6-117">Безопаснее создавать файл во время развертывания, если это возможно, а также предоставлять доступ `Read` к отдельному файлу вместо доступа `Create` к папке.</span><span class="sxs-lookup"><span data-stu-id="1f9d6-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f9d6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1f9d6-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- <span data-ttu-id="1f9d6-119">[How to: Read Object Data from an XML File (Visual Basic)](how-to-read-object-data-from-an-xml-file.md) (Практическое руководство. Чтение данных объекта из XML-файла (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="1f9d6-119">[How to: Read Object Data from an XML File (Visual Basic)](how-to-read-object-data-from-an-xml-file.md)</span></span>
- [<span data-ttu-id="1f9d6-120">Сериализация (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f9d6-120">Serialization (Visual Basic)</span></span>](index.md)
