---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: b004acb0c1c7d145c59a1e3a88ef7f1d405a91c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400567"
---
# <a name="-optionexplicit"></a>-optionexplicit
Заставляет компилятор сообщать об ошибках, если переменные не объявляются до их использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный элемент. Чтобы сделать явное объявление переменных обязательным, укажите `-optionexplicit+`. Параметр `-optionexplicit+` используется по умолчанию и аналогичен параметру `-optionexplicit`. Используйте параметр `-optionexplicit-`, чтобы разрешить неявное объявление переменных.  
  
## <a name="remarks"></a>Примечания  
 Если файл исходного кода содержит [оператор Option Explicit](../../language-reference/statements/option-explicit-statement.md), этот оператор переопределяет параметр компилятора командной строки `-optionexplicit`.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Как задать параметр -optionexplicit в интегрированной среде разработки Visual Studio  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.
  
2. Откройте вкладку **Компиляция**.  
  
3. Измените значение в поле **Option Explicit**.  
  
## <a name="example"></a>Пример  
 Следующий код компилируется, когда используется параметр `-optionexplicit-`.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-optioncompare](optioncompare.md)
- [-optionstrict](optionstrict.md)
- [-optioninfer](optioninfer.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [Оператор Option Explicit](../../language-reference/statements/option-explicit-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
