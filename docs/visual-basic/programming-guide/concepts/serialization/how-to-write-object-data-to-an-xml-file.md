---
title: Практическое руководство. Запись данных объекта в XML-файл
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: 9608a48cb8b3fac1c71affa7a0a17e9789f94b18
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413158"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a>How to: Write Object Data to an XML File (Visual Basic) (Практическое руководство. Запись данных объекта в XML-файл (Visual Basic))
Показывает, как записать объект из класса в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="compile-the-code"></a>Компиляция кода  
 У класса должен быть открытый конструктор без параметров.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
- В сериализуемом классе нет открытого конструктора без параметров.  
  
- Файл существует и является файлом только для чтения (<xref:System.IO.IOException>).  
  
- Слишком длинный путь (<xref:System.IO.PathTooLongException>).  
  
- Диск заполнен (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  
 В этом примере создается файл (если файл отсутствует). Если приложению требуется создать файл, оно должно иметь доступ к каталогу для создания файлов (`Create`). Если файл уже существует, то приложению достаточно иметь лишь доступ для записи файлов (`Write`), т. е. меньшие привилегии. Безопаснее создавать файл во время развертывания, если это возможно, а также предоставлять доступ `Read` к отдельному файлу вместо доступа `Create` к папке.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO.StreamWriter>
- [How to: Read Object Data from an XML File (Visual Basic)](how-to-read-object-data-from-an-xml-file.md) (Практическое руководство. Чтение данных объекта из XML-файла (Visual Basic))
- [Сериализация (Visual Basic)](index.md)
