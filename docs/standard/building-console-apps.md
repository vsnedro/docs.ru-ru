---
description: 'Узнайте подробнее о: Консольные приложения в .NET'
title: Создание консольных приложений в .NET
ms.date: 03/30/2017
helpviewer_keywords:
- .NET, creating console applications
- application development [.NET], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
ms.openlocfilehash: 9ebc0fbdc71cf0b6d30a07fc8a375899c5f55d52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676213"
---
# <a name="console-apps-in-net"></a>Консольные приложения в .NET

Приложения .NET могут использовать класс <xref:System.Console?displayProperty=nameWithType> для выполнения консольного ввода-вывода символов. Данные, поступающие от консоли, считываются из стандартного потока ввода, выводимые на консоль данные записываются в стандартный поток вывода, а сведения об ошибках записываются в стандартный поток вывода ошибок. Эти потоки автоматически связываются с консолью при запуске приложения и представлены свойствами <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> и <xref:System.Console.Error%2A> соответственно.

Значением свойства <xref:System.Console.In%2A?displayProperty=nameWithType> является объект <xref:System.IO.TextReader?displayProperty=nameWithType>, а значениями свойств <xref:System.Console.Out%2A?displayProperty=nameWithType> и <xref:System.Console.Error%2A?displayProperty=nameWithType> — объекты <xref:System.IO.TextWriter?displayProperty=nameWithType>. Эти свойства можно связывать с потоками, не представляющими консоль, что позволяет задать для любого из потоков другой источник или приемник данных. Например, можно перенаправить вывод в файл, присвоив свойству <xref:System.Console.Out%2A?displayProperty=nameWithType> объект <xref:System.IO.StreamWriter?displayProperty=nameWithType>, инкапсулирующий <xref:System.IO.FileStream?displayProperty=nameWithType> с помощью метода <xref:System.Console.SetOut%2A?displayProperty=nameWithType>. Свойства <xref:System.Console.In%2A?displayProperty=nameWithType> и <xref:System.Console.Out%2A?displayProperty=nameWithType> не обязательно должны быть связаны с одним потоком.

> [!NOTE]
> Дополнительные сведения о построении консольных приложений, включая образцы в C#, Visual Basic, и C++, см. в документации к классу <xref:System.Console>.

При отсутствии консоли, например в приложении Windows Forms, выводимые в стандартный поток вывода данные не отображаются для пользователя, так как их некуда выводить. Запись информации в недоступную консоль не приводит к возникновению исключения. (Вы всегда можете изменить тип приложения на **консольное приложение**, например на страницах свойств проекта в Visual Studio.)

У класса **System.Console** имеются методы, позволяющие считывать с консоли отдельные символы или целые строки. Другие методы выполняют преобразование данных и форматирование строковых значений, а затем выводят отформатированные строки на консоль. Дополнительные сведения о форматировании строк см. в статье [Типы форматирования](base-types/formatting-types.md).

> [!TIP]
> У консольных приложений отсутствует запускаемый по умолчанию механизм сообщений. Поэтому вызовы таймеров Microsoft Win32 из такого приложения могут завершаться неудачей.

## <a name="see-also"></a>См. также раздел

- <xref:System.Console?displayProperty=nameWithType>
- [Типы форматирования](base-types/formatting-types.md)
