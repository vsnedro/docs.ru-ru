---
title: Практическое руководство. Копирование каталогов
description: Сведения о том, как копировать каталоги с помощью классов ввода-вывода, осуществляющих синхронное копирование содержимого каталога в другое место.
ms.date: 12/27/2018
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
ms.openlocfilehash: b81723b9ed7067826692e8383bf64058d4295f0c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830835"
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
