---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: ac385880f8c13c23dffff67fc2a1ecc5609fd189
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581418"
---
# <a name="-optioncompare"></a>-optioncompare

Задает способ сравнения строк.

## <a name="syntax"></a>Синтаксис

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a>Примечания

Вы можете определить `-optioncompare` в одной из двух форм: `-optioncompare:binary`, чтобы использовать сравнения двоичных строк, и `-optioncompare:text`, чтобы использовать сравнения текстовых строк. По умолчанию компилятор использует `-optioncompare:binary`.

В Microsoft Windows текущая кодовая страница определяет порядок сортировки двоичных строк. Типичный порядок сортировки двоичных строк выглядит так:

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

Сравнение текстовых строк основано на порядке сортировки текста без учета регистра, что определяется языковым стандартом системы. Типичный порядок сортировки текстовых строк выглядит так:

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>Чтобы определить параметр -optioncompare в среде Visual Studio IDE, сделайте следующее:

1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.

2. Откройте вкладку **Компиляция**.

3. Измените значение поля **Сравнение параметров**.

### <a name="to-set--optioncompare-programmatically"></a>Чтобы определить параметр-optioncompare программными средствами, сделайте следующее:

См. сведения об [операторе Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md).

## <a name="example"></a>Пример

Следующий код компилирует `ProjFile.vb` и использует сравнение двоичных строк.

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
