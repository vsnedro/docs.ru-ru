---
title: Отладка ошибок StackOverflow
description: Сведения о диагностике исключений StackOverflow
ms.topic: tutorial
ms.date: 12/22/2020
ms.openlocfilehash: 92edf854ddcc2e778949d74eff1370cf27db25b4
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/24/2020
ms.locfileid: "97764933"
---
# <a name="debugging-stackoverflow-errors"></a>Отладка ошибок StackOverflow

Исключение <xref:System.StackOverflowException>, которое возникает при переполнении стека выполнения из-за чрезмерного количества вложенных вызовов метода.  

Например, рассмотрим представленное ниже приложение:

````
using System;

namespace temp
{
    class Program
    {
        static void Main(string[] args)
        {
            Main(args); // oops this recursion won't stop
        }
    }
}
````

Метод Main будет постоянно вызывать сам себя до тех пор, пока в стеке не закончится место.  После этого продолжение будет невозможно и возникнет исключение <xref:System.StackOverflowException>.  

````
> dotnet run
Stack overflow.
````

> [!NOTE]
> В .NET 5 и более поздних версий стек вызовов выводится на консоль.

> [!NOTE]
> В этой статье описывается отладка ситуаций переполнения стека с использованием lldb. Если вы работаете в Windows, для отладки приложения рекомендуется использовать [Visual Studio](/visualstudio/debugger/what-is-debugging) или [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging).  

## <a name="example"></a>Пример

1. Запуск приложения, для которого настроено получение дампа при аварийном завершении.

    ````
    > export COMPlus_DbgEnableMiniDump=1
    > dotnet run
    Stack overflow.
    Writing minidump with heap to file /tmp/coredump.6412
    Written 58191872 bytes (14207 pages) to core file
    ````

2. Установка расширения SOS с помощью [dotnet-sos](dotnet-sos.md).

    ````
    dotnet-sos install
    ````

3. Отладка дампа в lldb для просмотра стека сбоев.

    ````
    lldb --core /temp/coredump.6412
    (lldb) bt
    ...
        frame #261930: 0x00007f59b40900cc
        frame #261931: 0x00007f59b40900cc
        frame #261932: 0x00007f59b40900cc
        frame #261933: 0x00007f59b40900cc
        frame #261934: 0x00007f59b40900cc
        frame #261935: 0x00007f5a2d4a080f libcoreclr.so`CallDescrWorkerInternal at unixasmmacrosamd64.inc:867
        frame #261936: 0x00007f5a2d3cc4c3 libcoreclr.so`MethodDescCallSite::CallTargetWorker(unsigned long const*, unsigned long*, int) at callhelpers.cpp:70
        frame #261937: 0x00007f5a2d3cc468 libcoreclr.so`MethodDescCallSite::CallTargetWorker(this=<unavailable>, pArguments=0x00007ffe8222e7b0, pReturnValue=0x0000000000000000, cbReturnValue=0) at callhelpers.cpp:604
        frame #261938: 0x00007f5a2d4b6182 libcoreclr.so`RunMain(MethodDesc*, short, int*, PtrArray**) [inlined] MethodDescCallSite::Call(this=<unavailable>, pArguments=<unavailable>) at callhelpers.h:468
    ...
    ````

4. Верхний кадр `0x00007f59b40900cc` повторяется несколько раз. Используйте команду [SOS](sos-debugging-extension.md) `ip2md`, чтобы определить, какой метод находится по адресу `0x00007f59b40900cc`.

    ````
    (lldb) ip2md 0x00007f59b40900cc
    MethodDesc:   00007f59b413ffa8
    Method Name:          temp.Program.Main(System.String[])
    Class:                00007f59b4181d40
    MethodTable:          00007f59b4190020
    mdToken:              0000000006000001
    Module:               00007f59b413dbf8
    IsJitted:             yes
    Current CodeAddr:     00007f59b40900a0
    Version History:
      ILCodeVersion:      0000000000000000
      ReJIT ID:           0
      IL Addr:            0000000000000000
         CodeAddr:           00007f59b40900a0  (MinOptJitted)
         NativeCodeVersion:  0000000000000000
    Source file:  /temp/Program.cs @ 9
    ````

5. Просмотрите указанный метод temp.Program.Main(System.String[]) и источник "/temp/Program.cs @ 9", чтобы определить возможные ошибки. Если это не удается сделать, вы можете включить ведение журнала для этой области кода.

## <a name="see-also"></a>См. также:

* [Общие сведения о дампах в .NET](dumps.md)
* [Отладка дампов Linux](debug-linux-dumps.md)
* [Расширение отладки SOS для .NET](sos-debugging-extension.md)
