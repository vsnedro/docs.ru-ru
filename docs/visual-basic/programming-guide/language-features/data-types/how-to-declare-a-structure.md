---
description: Дополнительные сведения см. в статье как объявить структуру (Visual Basic)
title: Практическое руководство. Объявление структуры
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 7560f22db70fd5804ca309720d32477bcb9a3782
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436933"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Практическое руководство. Объявление структуры (Visual Basic)

Объявление структуры начинается с [оператора Structure](../../../language-reference/statements/structure-statement.md)и заканчивается `End Structure` инструкцией. Между этими двумя операторами необходимо объявить хотя бы один *элемент*. Элементы могут иметь любой тип данных, но хотя бы один из них должен быть либо необщей переменной, либо нестандартным, ненастраиваемым событием.  
  
 Нельзя инициализировать какие либо элементы структуры в объявлении структуры. При объявлении переменной, имеющей тип структуры, необходимо назначить значения элементам, обращаясь к ним через переменную.  
  
 Обсуждение различий между структурами и классами см. в разделе [структуры и классы](structures-and-classes.md).  
  
 В демонстрационных целях рассмотрим ситуацию, когда необходимо отследить имя сотрудника, телефонное расширение и заработную плату. Структура позволяет сделать это в одной переменной.  
  
### <a name="to-declare-a-structure"></a>Объявление структуры  
  
1. Создайте начальную и конечную инструкции для структуры.  
  
     Можно указать уровень доступа структуры с помощью ключевого слова [Public](../../../language-reference/modifiers/public.md), [protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)или [Private](../../../language-reference/modifiers/private.md) , либо можно разрешить по умолчанию использовать `Public` .  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. Добавьте элементы в текст структуры.  
  
     Структура должна содержать по крайней мере один элемент. Необходимо объявить каждый элемент и указать для него уровень доступа. Если вы используете [инструкцию Dim](../../../language-reference/statements/dim-statement.md) без ключевых слов, для специальных возможностей по умолчанию используется значение `Public` .  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     `salary`Поле в предыдущем примере имеет значение `Private` , которое означает, что оно недоступно за пределами структуры, даже из содержащего класса. Однако `giveRaise` процедура является `Public` , поэтому ее можно вызывать извне структуры. Аналогичным образом можно вызвать `salaryReviewTime` событие за пределами структуры.  
  
     Помимо переменных, процедур и `Sub` событий, в структуре можно также определять константы, `Function` процедуры и свойства. Можно назначить не более одного свойства в качестве *свойства по умолчанию* при условии, что оно принимает по крайней мере один аргумент. Можно выполнить обработку события с помощью [общей](../../../language-reference/modifiers/shared.md) `Sub` процедуры. Дополнительные сведения см. в разделе [инструкции. объявление и вызов свойства по умолчанию в Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>См. также раздел

- [Типы данных](index.md)
- [Простые типы данных](elementary-data-types.md)
- [Составные типы данных](composite-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Структуры](structures.md)
- [Устранение неполадок, связанных с типами данных](troubleshooting-data-types.md)
- [Переменные структуры](structure-variables.md)
- [Структуры и другие элементы программирования](structures-and-other-programming-elements.md)
- [Структуры и классы](structures-and-classes.md)
- [Тип данных, определенный пользователем](../../../language-reference/data-types/user-defined-data-type.md)
