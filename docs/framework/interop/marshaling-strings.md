---
title: Маршалинг строк
description: Узнайте, как маршалировать строки. См. параметры маршалирования строк по значению или ссылке в качестве результата в структуре или классе по значению или ссылке и т. д.
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
ms.openlocfilehash: 11925e3e126620788bb09e90e4d2528dbaf56581
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547770"
---
# <a name="marshaling-strings"></a>Маршалинг строк
При вызове неуправляемого кода копируются строковые аргументы, и при необходимости выполняется преобразование этих аргументов из формата .NET Framework (Юникод) в неуправляемый формат (ANSI). Так как управляемые строки являются неизменяемыми, то при вызове неуправляемого кода они не копируются обратно из неуправляемой памяти в управляемую память при возврате из функции.  
  
 В таблице ниже представлены варианты маршалинга строк, описано их использование и приведена ссылка на соответствующий пример кода .NET Framework.  
  
|Строка|Описание|Пример|  
|------------|-----------------|------------|  
|По значению.|Передает строки в качестве параметров In.|[MsgBox](msgbox-sample.md)|  
|Как результат.|Возвращает строки из неуправляемого кода.|[Строки](/previous-versions/dotnet/netframework-4.0/e765dyyy(v=vs.100))|  
|По ссылке.|Передает строки в качестве параметров In/Out с помощью <xref:System.Text.StringBuilder>.|[Buffers](/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100))|  
|В структуре по значению.|Передает строки в структуре, которая является параметром In.|[Структуры](/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100))|  
|В структуре по ссылке **(char\*)** .|Передает строки в структуре, которая является параметром In/Out. Неуправляемая функция ожидает указатель на символьный буфер, и размер буфера является членом структуры.|[Строки](/previous-versions/dotnet/netframework-4.0/e765dyyy(v=vs.100))|  
|В структуре по ссылке **(char[])** .|Передает строки в структуре, которая является параметром In/Out. Неуправляемая функция ожидает внедренный символьный буфер.|[OSInfo](/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|  
|В классе по значению **(char\*)** .|Передает строки в классе (класс является параметром In/Out). Неуправляемая функция ожидает указатель на символьный буфер.|[OpenFileDlg](/previous-versions/dotnet/netframework-4.0/w5tyztk9(v=vs.100))|  
|В классе по значению **(char[])** .|Передает строки в классе (класс является параметром In/Out). Неуправляемая функция ожидает внедренный символьный буфер.|[OSInfo](/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|  
|Как массив строк по значению.|Создает массив строк, который передается по значению.|[Массивы](marshaling-different-types-of-arrays.md)|  
|Как массив структур, содержащих строки по значению.|Создает массив структур, содержащих строки. Массив передается по значению.|[Массивы](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>См. также

- [Маршалинг по умолчанию для строк](default-marshaling-for-strings.md)
- [Маршалинг данных при вызове неуправляемого кода](marshaling-data-with-platform-invoke.md)
- [Маршалинг классов, структур и объединений](marshaling-classes-structures-and-unions.md)
- [Маршалинг различных типов массивов](marshaling-different-types-of-arrays.md)
- [Различные примеры маршалинга](/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))
