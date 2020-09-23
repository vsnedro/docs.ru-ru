---
title: Вложенные структуры управления
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: 290366d9d9428cefee108ac472fbe7c0eb66d82e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084168"
---
# <a name="nested-control-structures-visual-basic"></a>Вложенные структуры управления (Visual Basic)

Можно разместить управляющие операторы внутри других операторов управления, например `If...Then...Else` блока внутри `For...Next` цикла. Оператор управления, помещенный внутрь другой управляющей инструкции, называется *вложенным*.  
  
## <a name="nesting-levels"></a>Уровни вложенности  

 Структуры управления в Visual Basic могут быть вложены на столько уровней, сколько нужно. Распространенной практикой является более удобочитаемость вложенных структур путем создания отступов для текста каждой из них. Редактор интегрированной среды разработки (IDE) автоматически делает это.  
  
 В следующем примере процедура `sumRows` добавляет вместе положительные элементы каждой строки матрицы.  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 В предыдущем примере первая `Next` инструкция закрывает внутренний `For` цикл, а последняя `Next` инструкция закрывает внешний `For` цикл.  
  
 Аналогично, в вложенных `If` инструкциях `End If` инструкции автоматически применяются к ближайшей предыдущей `If` инструкции. Вложенные `Do` циклы работают аналогичным образом с самой внутренней `Loop` инструкцией, соответствующей самой внутренней `Do` инструкции.  
  
> [!NOTE]
> Для многих структур управления при щелчке ключевого слова все ключевые слова в структуре выделяются. Например, если щелкнуть `If` `If...Then...Else` конструкцию, `If` будут выделены все экземпляры,,, `Then` `ElseIf` `Else` и `End If` в конструкции. Чтобы перейти к следующему или предыдущему выделенному ключевому слову, нажмите клавиши CTRL + SHIFT + стрелка вниз или CTRL + SHIFT + стрелка вверх.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Вложение различных видов структур управления  

 Один тип структуры управления можно вложить в другой тип. В следующем примере используется `With` блок внутри `For Each` цикла и вложенные `If` блоки внутри `With` блока.  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>Перекрывающиеся структуры элементов управления  

 Нельзя перекрывать структуры управления. Это означает, что любая вложенная структура должна полностью содержаться в следующей самой внутренней структуре. Например, следующее расположение недопустимо, так как `For` цикл завершается до `With` завершения внутреннего блока.  
  
 ![Схема, на которой показан пример недопустимого вложения.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры элементов управления и сигнализирует об ошибке во время компиляции.  
  
## <a name="see-also"></a>См. также

- [Поток управления](index.md)
- [Структуры решений](decision-structures.md)
- [Циклические структуры](loop-structures.md)
- [Другие структуры управления](other-control-structures.md)
