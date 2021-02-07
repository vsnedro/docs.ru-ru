---
description: Дополнительные сведения см. в инструкции Option Explicit (Visual Basic)
title: Оператор Option Explicit
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 11f59508125167fde98b4fc359dde7fd7c539b75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741618"
---
# <a name="option-explicit-statement-visual-basic"></a>Оператор Option Explicit (Visual Basic)

Заставляет явно объявлять все переменные в файле или допускает неявные объявления переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Компоненты  

 `On`  
 Необязательный элемент. Включает `Option Explicit` проверку. Если параметр `On` или `Off` не указан, по умолчанию используется значение `On` .  
  
 `Off`  
 Необязательный элемент. Отключает `Option Explicit` проверку.  
  
## <a name="remarks"></a>Remarks  

 Если `Option Explicit On` или `Option Explicit` присутствует в файле, необходимо явно объявить все переменные с помощью `Dim` `ReDim` инструкций или. При попытке использовать необъявленное имя переменной во время компиляции возникает ошибка. `Option Explicit Off`Оператор допускает неявное объявление переменных.  
  
 Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.  
  
> [!NOTE]
> Установка `Option Explicit` в `Off` обычно не является хорошей практикой. Вы можете допустить ошибку при вводе имени переменной в одном или нескольких местах, что приведет к непредвиденным результатам при выполнении программы.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Если отсутствует оператор Option Explicit  

 Если исходный код не содержит `Option Explicit` инструкцию, то используется **параметр Explicit** на [странице Компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Если используется компилятор командной строки, используется параметр компилятора [-оптионексплиЦит](../../reference/command-line-compiler/optionexplicit.md) .  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Установка параметра Explicit в интегрированной среде разработки  
  
1. Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. Откройте вкладку **Компиляция**.  
  
3. Задайте значение в **явном поле Option** .  
  
 При создании нового проекта параметр **Option Explicit** на вкладке **Компиляция** имеет значение **Option Explicit** в диалоговом окне Параметры **VB по умолчанию** . Чтобы открыть диалоговое окно **настройки VB по умолчанию** , в меню **Сервис** выберите пункт **Параметры**. В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**. Начальным значением по умолчанию в **VB по умолчанию** является `On` .  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Установка параметра Explicit в командной строке  
  
- Включите параметр компилятора [-оптионексплиЦит](../../reference/command-line-compiler/optionexplicit.md) в команду **vbc** .  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `Option Explicit` для принудительного явного объявления всех переменных. Попытка использовать необъявленную переменную вызывает ошибку во время компиляции.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>См. также

- [Оператор Dim](dim-statement.md)
- [Оператор reDim](redim-statement.md)
- [Оператор Option Compare](option-compare-statement.md)
- [Оператор Option Strict](option-strict-statement.md)
- [-optioncompare](../../reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../reference/command-line-compiler/optionstrict.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
