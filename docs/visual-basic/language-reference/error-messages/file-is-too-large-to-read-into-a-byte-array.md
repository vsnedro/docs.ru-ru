---
description: 'Дополнительные сведения о: файл слишком большой для чтения в массив байтов'
title: Файл слишком велик для чтения в массив байтов
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 8b2eb7bcbbea42c56d607147e55d6c02695c5670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796292"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Файл слишком велик для чтения в массив байтов

Размер файла, который вы пытаетесь прочесть в массиве байтов, превышает 4 ГБ. `My.Computer.FileSystem.ReadAllBytes`Метод не может считать файл, размер которого превышает этот.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте <xref:System.IO.StreamReader> для чтения файла. Дополнительные сведения см. [в разделе основы платформа .NET Framework файлового ввода-вывода и файловой системы (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Доступ к файлам с помощью Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
- [Практическое руководство. Чтение текста из файлов с помощью StreamReader](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
