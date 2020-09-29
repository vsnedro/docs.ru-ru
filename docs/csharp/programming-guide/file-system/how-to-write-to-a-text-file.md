---
title: Руководство по программированию на C#. Запись в текстовый файл
description: Узнайте, как выполнить запись данных в текстовый файл на C#. Изучите несколько примеров кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: 48739852cd1730d71c3b20ae6a9394b57785faa6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170406"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Руководство по программированию на C#. Запись в текстовый файл

В этих примерах показаны различные способы записи текста в файл. В первых двух примерах используются удобные статические методы класса <xref:System.IO.File?displayProperty=nameWithType> для записи каждого элемента любого объекта `IEnumerable<string>` и строки в текстовый файл. В примере 3 показано, как добавить текст в файл, если необходимо обрабатывать отдельно каждую строку по мере ее записи в файл. В примерах 1–3 перезаписывается все существующее содержимое файла, а в примере 4 показано, как добавить текст в существующий файл.  
  
 Все эти примеры записывают строковые литералы в файлы. Чтобы отформатировать записываемый в файл текст, воспользуйтесь методом <xref:System.String.Format%2A> или функцией [интерполяции строк](../../language-reference/tokens/interpolated.md) C#.  
  
## <a name="example"></a>Пример  

 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 При следующих условиях возможно возникновение исключения:  
  
- Файл существует и является файлом только для чтения.  
  
- Имя пути имеет слишком большую длину.  
  
- Диск может быть переполнен.  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Файловая система и реестр (руководство по программированию на C#)](./index.md)
- [Пример. Сохранение коллекции настраиваемых объектов в локальном хранилище](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
