---
title: Практическое руководство. Запись в двоичные файлы
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: b36da82060b930101cb54dd852d050ac0155bd10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411555"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>Практическое руководство. Запись текста в двоичные файлы в Visual Basic

Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> записывает данные в двоичный файл. Если параметр `append` имеет значение `True`, данные будут добавляться в файл; в противном случае данные в файле перезаписываются.

Если указанный путь без имени файла является недопустимым, возникает исключение <xref:System.IO.DirectoryNotFoundException>. Если путь является допустимым, но файл не существует, файл будет создан.

## <a name="to-write-to-a-binary-file"></a>Запись в двоичный файл

Используйте метод `WriteAllBytes`, указав путь к файлу, имя файла и байты, которые требуется записать. В этом примере массив данных `CustomerData` добавляется в файл `CollectedData.dat`.

[!code-vb[VbVbcnMyFileSystem#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#27)]

## <a name="robust-programming"></a>Отказоустойчивость

Исключение может возникнуть при следующих условиях:

- Путь является недопустимым по одной из следующих причин: это строка нулевой длины; она содержит только пробелы; она содержит недопустимые знаки. (<xref:System.ArgumentException>).

- Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).

- `File` указывает на путь, который не существует (<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>).

- Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).

- Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).

- Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).

- У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [Практическое руководство. Запись текста в файлы](how-to-write-text-to-files.md)
