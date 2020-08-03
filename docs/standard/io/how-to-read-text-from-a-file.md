---
title: Практическое руководство. Чтение текста из файла
description: В этой статье приведены примеры синхронного и асинхронного чтения текста из текстового файла с помощью класса StreamReader в .NET для классических приложений.
ms.date: 01/03/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
ms.openlocfilehash: 0d8dfae67ede779a611204fb333a19defcaee8e6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382130"
---
# <a name="how-to-read-text-from-a-file"></a>Практическое руководство. Чтение текста из файла
В следующих примерах демонстрируется синхронное и асинхронное чтение текста из текстового файла с использованием .NET для классических приложений. В обоих примерах при создании экземпляра класса <xref:System.IO.StreamReader> указывается относительный или абсолютный путь к файлу.
  
> [!NOTE]
> Эти примеры кода не относятся к разработке приложений Universal Windows (UWP), поскольку в среде выполнения Windows используются разные типы потоков для чтения и записи файлов. Пример чтения текста из файла в приложении UWP см. в разделе [Краткое руководство. Чтение и запись файлов](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)). Примеры, демонстрирующие преобразование потоков .NET Framework в потоки среды выполнения Windows и наоборот, см. в разделе [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example-synchronous-read-in-a-console-app"></a>Пример. Синхронное чтение в консольном приложении  
Следующий пример иллюстрирует синхронную операцию чтения в консольном приложении. В этом примере текстовый файл открывается с помощью модуля чтения потока, содержимое копируется в строку, а строка выводится в консоли.  
  
> [!IMPORTANT]
> В примерах предполагается, что файл с именем *TestFile.txt* уже существует в той же папке, что и приложение.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/sync-console/Program.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/sync-console/Program.vb":::
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>Пример. Асинхронное чтение в приложении WPF
 Следующий пример иллюстрирует асинхронную операцию чтения в приложении Windows Presentation Foundation (WPF).  
  
> [!IMPORTANT]
> В примерах предполагается, что файл с именем *TestFile.txt* уже существует в той же папке, что и приложение.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/async-wpf/MainWindow.xaml.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/async-wpf/MainWindow.xaml.vb":::
  
## <a name="see-also"></a>См. также

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [Асинхронный файловый ввод-вывод](asynchronous-file-i-o.md)  
- [Практическое руководство. Создание списка каталогов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Краткое руководство. Чтение и запись файлов](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [Практическое руководство. Считывание данных из нового файла и запись в этот файл](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Практическое руководство. Открытие файла журнала и добавление в него данных](how-to-open-and-append-to-a-log-file.md)  
- [Практическое руководство. Запись текста в файл](how-to-write-text-to-a-file.md)  
- [Практическое руководство. Считывание символов из строки](how-to-read-characters-from-a-string.md)  
- [Практическое руководство. Запись символов в строку](how-to-write-characters-to-a-string.md)  
- [Файловый и потоковый ввод-вывод](index.md)
