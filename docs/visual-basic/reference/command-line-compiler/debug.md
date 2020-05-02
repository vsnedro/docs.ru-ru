---
title: -debug
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: df65d1c095f5a22d562d78e15baf750a20ec2556
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716778"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)

Компилятор создает отладочную информацию и помещает ее в один или несколько выходных файлов.

## <a name="syntax"></a>Синтаксис

```console
-debug[+ | -]
```

or

```console
-debug:[full | pdbonly]
```

## <a name="arguments"></a>Аргументы

|Термин|Определение|
|---|---|
|`+` &#124; `-`|Необязательный элемент. Задание значения `+` или `-debug` включает создание компилятором отладочной информации, которая помещается в файл PDB. Указание `-` дает тот же результат, что и отсутствие `-debug`.|
|`full` &#124; `pdbonly`|Необязательный элемент. Определяет тип отладочной информации, создаваемой компилятором. Если не указать `-debug:pdbonly`, по умолчанию используется значение `full`, что позволяет подключить отладчик к выполняющейся программе. Аргумент `pdbonly` позволяет выполнять отладку исходного кода при запуске программы в отладчике, но при этом код на языке ассемблера отображается только при подключении выполняющейся программы к отладчику.|

## <a name="remarks"></a>Примечания

Используйте этот параметр для создания отладочных сборок. Если не указать `-debug`, `-debug+` или `-debug:full`, вы не сможете выполнить отладку выходного файла программы.

По умолчанию отладочная информация не выводится (`-debug-`). Чтобы вывести отладочную информацию, укажите `-debug` или `-debug+`.

Сведения о настройке производительности отладки для приложения см. в разделе [Упрощение отладки образов](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).

|Порядок задания параметра -debug в интегрированной среде разработки Visual Studio|
|---|
|1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Щелкните **Дополнительные параметры компиляции**.<br />4.  Измените значение в поле **Создавать отладочную информацию**.|

## <a name="example"></a>Пример

Следующий пример помещает отладочную информацию в выходной файл `App.exe`.

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
