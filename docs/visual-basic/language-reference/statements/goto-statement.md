---
description: 'Дополнительные сведения о инструкции: GoTo'
title: Оператор GoTo
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 804baec130111562225b09cbdc7b5fb2d73adba5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769056"
---
# <a name="goto-statement"></a>Оператор GoTo

Безусловно подразделяется на указанную строку в процедуре.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Отделение  

 `line`  
 Обязательный элемент. Метка любой линии.  
  
## <a name="remarks"></a>Remarks  

 `GoTo`Оператор может создать ветвь только для строк в процедуре, в которой она отображается. Строка должна иметь метку, которая `GoTo` может ссылаться на. Дополнительные сведения см. [в разделе инструкции. Метки](../../programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> `GoTo` инструкции могут усложнить чтение и поддержку кода. Везде, где это возможно, следует использовать структуру элементов управления. Дополнительные сведения см. в разделе [Поток управления](../../programming-guide/language-features/control-flow/index.md).  
  
 Нельзя использовать `GoTo` оператор для ветвления извне `For` ... `Next` , `For Each` ... `Next` , `SyncLock` ... `End SyncLock` , `Try` . `Catch` .. ... `Finally` , `With` ... `End With` или `Using` ... `End Using` конструкция к метке внутри.  
  
## <a name="branching-and-try-constructions"></a>Ветвление и конструкции try  

 В `Try` ... `Catch` ...`Finally` для создания ветвления с помощью оператора применяются следующие правила `GoTo` .  
  
|Блок или область|Ветвление вне|Ветвление из внутрь|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` блок|Только из `Catch` блока одной конструкции <sup>1</sup>|Только за пределами всей конструкции|  
|`Catch` блок|Никогда не разрешено|Только за пределами всей конструкции или с `Try` блоком той же конструкции <sup>1</sup>|  
|`Finally` блок|Никогда не разрешено|Никогда не разрешено|  
  
 <sup>1</sup> , если один `Try` ... `Catch` ...`Finally` Конструкция вложена в другую, `Catch` блок может выполнять ветвление в `Try` блок на своем собственном уровне вложенности, но не в другой `Try` блок. Вложенный `Try` ... `Catch` ...`Finally` конструкция должна полностью содержаться в `Try` `Catch` блоке или конструкции, внутри которой она вложена.  
  
 На следующем рисунке показана одна `Try` конструкция, вложенная в другую. Различные ветви между блоками двух конструкций указываются как допустимые или недопустимые.  
  
 ![Графическая схема ветвления в конструкциях Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `GoTo` для перехода к меткам линии в процедуре.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>См. также

- [Оператор Do…Loop](do-loop-statement.md)
- [Оператор For…Next](for-next-statement.md)
- [Оператор For Each…Next](for-each-next-statement.md)
- [Оператор If…Then…Else](if-then-else-statement.md)
- [Оператор Select…Case](select-case-statement.md)
- [Оператор Try...Catch...Finally](try-catch-finally-statement.md)
- [Оператор While…End While](while-end-while-statement.md)
- [Оператор With…End With](with-end-with-statement.md)
