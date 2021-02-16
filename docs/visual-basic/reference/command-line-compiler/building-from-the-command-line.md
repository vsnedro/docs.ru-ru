---
description: 'Узнайте подробнее о: Построение из командной строки (Visual Basic)'
title: Построение из командной строки
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: 5f0f8dd61bd5b79987cc1e59dcf4bfd8071a925e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468269"
---
# <a name="building-from-the-command-line-visual-basic"></a>Построение из командной строки (Visual Basic)

Проект Visual Basic состоит из одного или нескольких отдельных исходных файлов. В ходе процесса, который называется компиляцией, эти файлы объединяются в один пакет — единый исполняемый файл, который можно запускать как приложение.

Visual Basic предоставляет компилятор командной строки, который можно использовать вместо компиляции программ в интегрированной среде разработки Visual Studio. Компилятор командной строки предназначен для ситуаций, в которых вам не требуется полный набор функций интегрированной среды разработки, — например, когда вы используете компьютеры с ограниченным объемом системной памяти или дискового пространства или пишете код для таких компьютеров.

Чтобы скомпилировать исходные файлы в интегрированной среде разработки Visual Studio, выберите команду **Выполнить сборку** в меню **Сборка**.

> [!TIP]
> При сборке файлов проекта в интегрированной среде разработки Visual Studio можно вывести сведения о соответствующей команде **vbc** и ее параметрах в окне вывода. Чтобы отобразить эти сведения, откройте [диалоговое окно "Параметры", последовательно выберите пункты "Проекты и решения", "Сборка и запуск"](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), а затем установите для параметра **Уровень детализации выходных данных сборки проекта MSBuild** значение **Обычный** или выберите более высокий уровень детализации. Дополнительные сведения см. в разделе [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).

Файлы проекта (с расширением VBPROJ) можно компилировать в командной строке с помощью MSBuild. Дополнительные сведения см. в [справочнике по командной строке](/visualstudio/msbuild/msbuild-command-line-reference) и [пошаговом руководстве в Visual Studio](/visualstudio/msbuild/walkthrough-using-msbuild).

## <a name="in-this-section"></a>В этом разделе

[Практическое руководство. Вызов компилятора командной строки](how-to-invoke-the-command-line-compiler.md) \
Описание вызова компилятора командной строки в командной строке MS-DOS или из определенного подкаталога.

[Примеры командных строк компиляции](sample-compilation-command-lines.md) \
Список примеров командных строк, которые можно изменять для использования в своих целях.

## <a name="related-sections"></a>Связанные разделы

[Компилятор Visual Basic с интерфейсом командной строки](index.md) \
Списки параметров компилятора, упорядоченных в алфавитном порядке или по назначению.

[Условная компиляция](../../programming-guide/program-structure/conditional-compilation.md) \
Описание компиляции отдельных разделов кода.

[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \ (Построение и очистка проектов и решений в Visual Studio)
Описание, как можно упорядочивать то, что будет включено в различные сборки, выбирать свойства проекта и проверять правильность порядка сборки проектов.
