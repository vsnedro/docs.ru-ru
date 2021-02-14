---
description: Дополнительные сведения см. в статье как читать данные объекта из XML-файла (Visual Basic)
title: Практическое руководство. Чтение данных объекта из XML-файла
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: d281997a0dd96ad6263fe03cea84b3e84005a3ad
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486827"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>How to: Read Object Data from an XML File (Visual Basic) (Практическое руководство. Чтение данных объекта из XML-файла (Visual Basic))

В этом примере демонстрируется считывание данных объекта, которые ранее были записаны в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="example"></a>Пример  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compile-the-code"></a>Компиляция кода  

 Замените имя файла "c:\temp\SerializationOverview.xml" на имя файла, в котором содержатся сериализованные данные. Дополнительные сведения о сериализации данных см. [в разделе инструкции. запись данных объекта в XML-файл (Visual Basic)](how-to-write-object-data-to-an-xml-file.md).  
  
 У класса должен быть открытый конструктор без параметров.  
  
 Десериализуются только открытые свойства и поля.  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 При следующих условиях возможно возникновение исключения:  
  
- В сериализуемом классе нет открытого конструктора без параметров.  
  
- Данные в файле не являются данными из класса, который десериализуется.  
  
- Файл не существует (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  

 Всегда проверяйте входные данные и никогда не десериализуйте данные из непроверенных источников. Созданный заново объект выполняется на локальном компьютере с разрешениями кода, который его десериализовал. Следует проверять все входные данные перед использованием их в приложении.  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.StreamWriter>
- [How to: Write Object Data to an XML File (Visual Basic)](how-to-write-object-data-to-an-xml-file.md) (Практическое руководство. Запись данных объекта в XML-файл (Visual Basic))
- [Сериализация (Visual Basic)](index.md)
- [Руководство по программированию на Visual Basic](../../index.md)
