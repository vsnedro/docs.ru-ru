---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: 3dd12971a082869c32b6292ed45e2014b8b0e2c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400543"
---
# <a name="-optionstrict"></a>-optionstrict

Применяет строгую семантику типа, чтобы ограничить неявные преобразования типов.

## <a name="syntax"></a>Синтаксис

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a>Аргументы

`+` &#124; `-`  
Необязательный элемент. Параметр `-optionstrict+` ограничивает неявное преобразование типов. Значение этого параметра по умолчанию равно `-optionstrict-`. Параметр `-optionstrict+` совпадает с `-optionstrict`. Для нестрогой семантики типов можно использовать и тот, и другой.

`custom`  
Обязательный. Предупреждать, когда не накладывается ограничение на строгую семантику языка.

## <a name="remarks"></a>Примечания

Если применяется `-optionstrict+`, только расширяющие преобразования типов могут быть выполнены неявно. Неявные сужающие преобразования типов, такие как назначение объекта типа `Decimal` объекту целочисленного типа, регистрируются как ошибки.

Чтобы создать предупреждения для неявных сужающих преобразований типов, используйте `-optionstrict:custom`. Используйте `-nowarn:numberlist`, чтобы пропускать определенные предупреждения, и `-warnaserror:numberlist`, чтобы обрабатывать определенные предупреждения как ошибки.

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Порядок задания параметра -optionstrict в среде Visual Studio IDE

1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.

2. Откройте вкладку **Компиляция**.

3. Измените значение в поле **Option Strict**.

### <a name="to-set--optionstrict-programmatically"></a>Порядок задания параметра -optionstrict программным образом

См. раздел [Оператор Option Strict](../../language-reference/statements/option-strict-statement.md).

## <a name="example"></a>Пример

Следующий код компилирует `Test.vb` с использованием строгой семантики типов.

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-optioncompare](optioncompare.md)
- [-optionexplicit](optionexplicit.md)
- [-optioninfer](optioninfer.md)
- [-nowarn](nowarn.md)
- [-warnaserror (Visual Basic)](warnaserror.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [Оператор Option Strict](../../language-reference/statements/option-strict-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
