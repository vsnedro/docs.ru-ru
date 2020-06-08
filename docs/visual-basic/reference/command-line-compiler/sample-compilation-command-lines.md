---
title: Примеры командных строк компиляции
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 496627d3b77b0382ae7d15c8225a6fbd41f1db73
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403126"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Примеры командных строк компиляции (Visual Basic)

В качестве альтернативы компиляции Visual Basic программ из Visual Studio можно выполнить компиляцию из командной строки, чтобы создать исполняемые файлы (EXE) или файлы библиотеки динамической компоновки (DLL).

Компилятор командной строки Visual Basic поддерживает полный набор параметров, управляющих входными и выходными файлами, сборками, а также параметрами отладки и препроцессора. Каждый параметр доступен в двух взаимозаменяемых формах: `-option` и `/option`. В этой документации приводится только форма `-option`.

В следующей таблице приведены некоторые примеры командных строк, которые можно изменять для использования в своих целях.

|Кому|Использовать|
|--------|---------|
|Компиляция файла File.vb и создание файла File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|Компиляция файла File.vb и создание файла File.dll|`vbc -target:library File.vb`|
|Компиляция файла File.vb и создание файла My.exe|`vbc -out:My.exe File.vb`|
|Компиляция файла File.vb и создание библиотеки и базовой сборки с именем File.dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Компиляция всех файлов Visual Basic в текущем каталоге с включенными оптимизациями и заданным символом `DEBUG`, ведущая к созданию файла File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|Компиляция всех файлов Visual Basic в текущем каталоге, ведущая к созданию отладочной версии библиотеки File2.dll без отображения логотипа или предупреждений|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|Компиляция всех файлов Visual Basic в текущем каталоге в файл Something.dll|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> При сборке проекта в интегрированной среде разработки Visual Studio можно вывести сведения о соответствующей команде **vbc** и ее параметрах компилятора в окне вывода. Чтобы отобразить эти сведения, откройте [диалоговое окно "Параметры", последовательно выберите пункты "Проекты и решения", "Сборка и запуск"](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), а затем установите для параметра **Уровень детализации выходных данных сборки проекта MSBuild** значение **Обычный** или выберите более высокий уровень детализации.

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Условная компиляция](../../programming-guide/program-structure/conditional-compilation.md)
