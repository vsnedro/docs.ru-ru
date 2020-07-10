---
title: Практическое руководство. Чтение метаданных изображения
desription: Learn how to read the Windows Forms PropertyItems property of an Image object to retrieve all the metadata from a file.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 814cb17feba1e1e3a42b2bc403b0b4c828caf90e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174670"
---
# <a name="how-to-read-image-metadata"></a>Практическое руководство. Чтение метаданных изображения

Некоторые файлы изображений содержат метаданные, которые можно прочитать, чтобы определить характеристики изображения. Например, цифровая фотография может содержать метаданные, которые можно прочитать для определения марки и модели камеры, используемой для записи образа. С помощью GDI+ можно считывать существующие метаданные, а также записывать новые метаданные в файлы изображений.

GDI+ сохраняет отдельный элемент метаданных в <xref:System.Drawing.Imaging.PropertyItem> объекте. <xref:System.Drawing.Image.PropertyItems%2A> <xref:System.Drawing.Image> Чтобы получить все метаданные из файла, можно прочитать свойство объекта. <xref:System.Drawing.Image.PropertyItems%2A>Свойство возвращает массив <xref:System.Drawing.Imaging.PropertyItem> объектов.

<xref:System.Drawing.Imaging.PropertyItem>Объект имеет следующие четыре свойства: `Id` , `Value` , `Len` и `Type` .

## <a name="id"></a>Идентификатор

Тег, определяющий элемент метаданных. Некоторые значения, которые могут быть назначены, <xref:System.Drawing.Imaging.PropertyItem.Id%2A> показаны в следующей таблице:

|Шестнадцатеричное значение|Описание|
|-----------------------|-----------------|
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Название образа<br /><br /> Производитель оборудования<br /><br /> Модель оборудования<br /><br /> ексифдторигинал<br /><br /> Время экспозиции EXIF<br /><br /> Таблица освещенности<br /><br /> Таблица чроминанце|

## <a name="value"></a>Значение

Массив значений типа . Формат значений определяется <xref:System.Drawing.Imaging.PropertyItem.Type%2A> свойством.

## <a name="len"></a>Len

Длина (в байтах) массива значений, на который указывает <xref:System.Drawing.Imaging.PropertyItem.Value%2A> свойство.

## <a name="type"></a>Тип

Тип данных значений в массиве, на который указывает `Value` свойство. Форматы, указанные `Type` значениями свойств, показаны в следующей таблице.

|Числовое значение|Описание|
|-------------------|-----------------|
|1|Выполнение команды `Byte`|
|2|Массив `Byte` объектов, закодированных как ASCII|
|3|16-разрядное целое число|
|4|32-разрядное целое число|
|5|Массив из двух `Byte` объектов, представляющих рациональное число|
|6|Не используется|
|7|Не определено|
|8|Не используется|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>Пример
  
Следующий пример кода считывает и отображает семь элементов метаданных в файле `FakePhoto.jpg` . Второй элемент свойства (index 1) в списке имеет <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (производитель оборудования) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (массив байтов в кодировке ASCII). В примере кода отображается значение этого элемента свойства.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

Код выводит примерно следующий результат:

```output
 Property Item 0
  
 id: 0x320
  
 type: 2

 length: 16 bytes
  
 Property Item 1
  
 id: 0x10f
  
 type: 2
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```

## <a name="compiling-the-code"></a>Компиляция кода

Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e` , что является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий. Обработайте <xref:System.Windows.Forms.Control.Paint> событие формы и вставьте этот код в обработчик событий Paint. Необходимо заменить на `FakePhoto.jpg` имя образа и путь, допустимые в системе, и импортировать `System.Drawing.Imaging` пространство имен.

## <a name="see-also"></a>См. также раздел

- [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](images-bitmaps-and-metafiles.md)
- [Работа с растровыми и векторными изображениями](working-with-images-bitmaps-icons-and-metafiles.md)
