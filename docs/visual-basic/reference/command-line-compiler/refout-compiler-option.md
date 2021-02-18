---
description: 'Дополнительные сведения: -refout (Visual Basic)'
title: -refout
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 2760f7e60d950aaff90becad843824a2e2b4379f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474126"
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

Параметр **-refout** указывает путь к файлу, в который нужно выводить базовую сборку.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Синтаксис

```console
-refout:filepath
```

## <a name="arguments"></a>Аргументы

`filepath`  
Путь и имя файла базовой сборки. Обычно этот файл находится в подпапке основной сборки. Согласно рекомендуемому соглашению (используемому в MSBuild), базовую сборку следует помещать во вложенную папку ref/ относительно основной сборки. Все папки в пути `filepath` должны существовать; компилятор не создает их.

## <a name="remarks"></a>Примечания

Поддержка параметра `-refout` в Visual Basic появилась в версии 15.3.

Базовые сборки являются особым типом сборки, которая содержит только минимальный объем метаданных, необходимый для представления общедоступного API-интерфейса библиотеки. Такие сборки включают в себя объявления для всех элементов, которые важны при указании ссылки на сборку в средствах сборки, но исключают все реализации элементов, а также объявления закрытых элементов, не имеющих наблюдаемого влияния на их контракт API. Дополнительные сведения см. в разделе [Базовые сборки](../../../standard/assembly/reference-assemblies.md) в руководстве по .NET.

Параметры `-refout` и [`-refonly`](refonly-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также

- [/refonly](refonly-compiler-option.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
