---
title: Файл слишком велик для чтения в массив байтов
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: b81fc9332d5f1347404fcdd73bce72b6b09778b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363128"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Файл слишком велик для чтения в массив байтов
Размер файла, который вы пытаетесь прочесть в массиве байтов, превышает 4 ГБ. `My.Computer.FileSystem.ReadAllBytes`Метод не может считать файл, размер которого превышает этот.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте <xref:System.IO.StreamReader> для чтения файла. Дополнительные сведения см. [в разделе основы .NET Framework файлового ввода-вывода и файловой системы (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Доступ к файлам с помощью Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
- [Практическое руководство. Чтение текста из файлов с помощью StreamReader](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
