---
description: '#nullable — справочник по C#'
title: '#nullable — справочник по C#'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099451"
---
# <a name="nullable-c-reference"></a>nullable (справочник по C#)

Директива препроцессора `#nullable` устанавливает контекст с *заметками о допустимости значений NULL* и *контекст с предупреждениями о допустимости значений NULL*. Эта директива определяет, действуют ли заметки, допускающие значение NULL, и могут ли быть заданы предупреждения о допустимости значений NULL. Каждый контекст либо *отключен*, либо *включен*.

Оба контекста можно указать на уровне проекта (за пределами исходного кода C#). Директива `#nullable` управляет контекстами заметок и предупреждений и имеет приоритет над параметрами уровня проекта. Директива задает контексты, которыми управляет, пока другая директива не переопределит ее, или до конца исходного файла.

Ниже приведены результаты использования директив:

- `#nullable disable`: задает контексты с заметками и предупреждениями о допустимости значения NULL в значение *отключено*.
- `#nullable enable`: задает контексты с заметками и предупреждениями о допустимости значения NULL в значение *включено*.
- `#nullable restore`: восстанавливает контексты с заметками и предупреждениями о допустимости значения NULL до параметров проекта.
- `#nullable disable annotations`: устанавливает контекст с заметками о допустимости значения NULL в режим *отключено*.
- `#nullable enable annotations`: устанавливает контекст с заметками о допустимости значения NULL в режим *включено*.
- `#nullable restore annotations`: восстанавливает контексты с заметками о допустимости значения NULL до параметров проекта.
- `#nullable disable warnings`: устанавливает контекст с предупреждениями о допустимости значения NULL в режим *отключено*.
- `#nullable enable warnings`: устанавливает контекст с предупреждениями о допустимости значения NULL в режим *включено*.
- `#nullable restore warnings`: восстанавливает контексты с предупреждениями о допустимости значения NULL до параметров проекта.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)