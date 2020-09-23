---
title: Константы, определенные пользователем
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 351bdb6963e278341c13e53ef19aea0876010aa9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095646"
---
# <a name="user-defined-constants-visual-basic"></a>Константы, определенные пользователем (Visual Basic)

Константа — это понятное имя, которое принимает позицию числа или строки, которые не меняются. Как можно понять из их названия, константы хранят значения, которые остаются постоянными в ходе выполнения приложения. Вы можете использовать константы, определенные элементами управления или компонентами, с которыми вы работаете, или создать собственный. Константы, созданные самостоятельно, описаны как *определяемые пользователем*.  
  
 Вы объявляете константу с `Const` инструкцией, используя те же рекомендации, что и при создании имени переменной. Если `Option Strict` имеет значение `On` , необходимо явно объявить константный тип.  
  
## <a name="const-statement-usage"></a>Использование инструкции const  

 `Const`Оператор может представлять математическое или значение даты и времени:  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 Он также может определять `String` константы:  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 Выражение в правой части знака равенства ( `=` ) часто представляет собой число или литеральную строку, но оно также может быть выражением, результатом которого является число или строка (хотя это выражение не может содержать вызовы функций). Константы можно даже определять с точки зрения ранее определенных констант:  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a>Область определяемых пользователем констант  

 `Const`Область действия инструкции аналогична области видимости переменной, объявленной в том же расположении. Указать область можно одним из следующих способов.  
  
- Чтобы создать константу, которая существует только в пределах процедуры, объявите ее внутри этой процедуры.  
  
- Чтобы создать константу, доступную для всех процедур в классе, но не для кода за пределами этого модуля, объявите ее в разделе Declarations класса.  
  
- Чтобы создать константу, доступную всем членам сборки, но не внешним клиентам сборки, объявите ее с помощью `Friend` ключевого слова в разделе Declarations класса.  
  
- Чтобы создать константу, доступную во всем приложении, объявите ее с помощью `Public` ключевого слова в разделе объявлений класс.  
  
 Дополнительные сведения см. [в разделе инструкции. Объявление константы](how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Предотвращение циклических ссылок  

 Поскольку константы могут быть определены с точки зрения других констант, можно случайно создать *цикл*или циклическую ссылку между двумя или более константами. Цикл происходит при наличии двух или более открытых констант, каждая из которых определена в терминах другого, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 При возникновении цикла Visual Basic выдает ошибку компилятора.  
  
## <a name="see-also"></a>См. также

- [Оператор Const](../../../language-reference/statements/const-statement.md)
- [Типы данных констант и литералов](constant-and-literal-data-types.md)
- [Константы и перечисления](index.md)
- [Константы и перечисления](../../../language-reference/constants-and-enumerations.md)
- [Общие сведения о перечислениях](enumerations-overview.md)
- [Общие сведения о константах](constants-overview.md)
- [Практическое руководство. Объявление перечисления](how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
