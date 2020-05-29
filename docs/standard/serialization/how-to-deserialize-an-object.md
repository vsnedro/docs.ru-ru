---
title: Десериализация объекта с помощью XmlSerializer
description: Узнайте, как выполнить десериализацию объекта. Формат передачи определяет, создается поток или объект файла.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: e08ae0d77539219223650fd3bcbd1bcee4df2739
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379116"
---
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a>Десериализация объекта с помощью XmlSerializer

При десериализации объекта формат передачи определяет, создается поток или объект файла. Определив формат передачи, можно вызвать методы <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> или <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> в зависимости от необходимости.

## <a name="to-deserialize-an-object"></a>Десериализация объекта

1. Постройте <xref:System.Xml.Serialization.XmlSerializer> с использованием типа сериализуемого объекта.

1. Вызовите метод <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, чтобы создать реплику объекта. При десериализации следует приводить возвращенный объект к типу исходного, как показано в следующем примере, десериализующем объект из файла (хотя его также можно десериализовать из потока).

    ```vb
    ' Construct an instance of the XmlSerializer with the type
    ' of object that is being deserialized.
    Dim mySerializer As New XmlSerializer(GetType(MySerializableClass))
    ' To read the file, create a FileStream.
    Dim myFileStream As New FileStream("myFileName.xml", FileMode.Open)
    ' Call the Deserialize method and cast to the object type.
    Dim myObject = CType( _
    mySerializer.Deserialize(myFileStream), MySerializableClass)
    ```

    ```csharp
    // Construct an instance of the XmlSerializer with the type
    // of object that is being deserialized.
    var mySerializer = new XmlSerializer(typeof(MySerializableClass));
    // To read the file, create a FileStream.
    var myFileStream = new FileStream("myFileName.xml", FileMode.Open);
    // Call the Deserialize method and cast to the object type.
    var myObject = (MySerializableClass) mySerializer.Deserialize(myFileStream)
    ```

## <a name="see-also"></a>См. также

- [Введение в сериализацию XML](introducing-xml-serialization.md)
- [Практическое руководство. Сериализация объекта](how-to-serialize-an-object.md)
