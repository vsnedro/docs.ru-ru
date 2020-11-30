---
title: Практическое руководство. Считывание символов из строки
description: Узнайте, как считывать символы из строки в .NET. Ознакомьтесь с примерами синхронного и асинхронного чтения символов.
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
ms.openlocfilehash: beb3f4f38a5c28d19eff6fece5a6bb3c4e7a9c48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734573"
---
# <a name="how-to-read-characters-from-a-string"></a>Практическое руководство. Считывание символов из строки

Следующий пример кода демонстрирует синхронное и асинхронное чтение символов из строки.  
  
## <a name="example-read-characters-synchronously"></a>Пример. Синхронное чтение символов

 Этот пример синхронным образом считывает 13 символов из строки, сохраняет их в массиве и отображает. Затем он считывает остальные символы строки, сохраняет их в массив, начиная с шестого элемента, и отображает содержимое массива.  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a>Пример. Асинхронное чтение символов  

 Ниже приведен пример кода за приложением WPF. При загрузке окна пример асинхронным способом считывает все символы из элемента управления <xref:System.Windows.Controls.TextBox> и сохраняет их в массиве. Затем он асинхронно записывает все буквы и пробелы в элемент управления <xref:System.Windows.Controls.TextBlock>, размещая их на отдельных строках.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [Асинхронный файловый ввод-вывод](asynchronous-file-i-o.md)  
- [Практическое руководство. Создание списка каталогов](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Практическое руководство. Считывание данных из нового файла и запись в этот файл](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Практическое руководство. Открытие файла журнала и добавление в него данных](how-to-open-and-append-to-a-log-file.md)  
- [Практическое руководство. Чтение текста из файла](how-to-read-text-from-a-file.md)  
- [Практическое руководство. Запись текста в файл](how-to-write-text-to-a-file.md)  
- [Практическое руководство. Запись символов в строку](how-to-write-characters-to-a-string.md)  
- [Файловый и потоковый ввод-вывод](index.md)
