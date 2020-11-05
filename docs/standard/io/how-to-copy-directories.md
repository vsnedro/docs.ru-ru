---
title: Практическое руководство. Копирование каталогов
description: Сведения о том, как копировать каталоги с помощью классов ввода-вывода, осуществляющих синхронное копирование содержимого каталога в другое место.
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET], copying directories
- subdirectory copying
- copying directories
- directories [.NET], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: 476473d5c25ce29d070abbeef7fa29a7cb9621e1
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187987"
---
# <a name="how-to-copy-directories"></a>Практическое руководство. Копирование каталогов

В этой статье демонстрируется использование классов ввода-вывода для синхронного копирования содержимого каталога в другое место.

Пример асинхронного копирования файлов см. в разделе [Асинхронный файловый ввод-вывод](asynchronous-file-i-o.md).

В этом примере для копирования подкаталогов объекту `copySubDirs` метода `DirectoryCopy` присваивается значение `true`. Метод `DirectoryCopy` выполняет рекурсивное копирование подкаталогов путем вызова самого себя для каждого последующего подкаталога, пока не будет скопировано все.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a>См. также

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [Файловый и потоковый ввод-вывод](index.md)
- [Распространенные задачи ввода-вывода](common-i-o-tasks.md)
- [Асинхронный файловый ввод-вывод](asynchronous-file-i-o.md)
