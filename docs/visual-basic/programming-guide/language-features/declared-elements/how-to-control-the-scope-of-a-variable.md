---
title: Практическое руководство. Управление областью действия переменной
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 2ce7c1700eec54542719e6e0880466ca136e86f6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095437"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Практическое руководство. Управление областью действия переменной (Visual Basic)

Как правило, переменная находится в *области видимости*или видима для справки по всему региону, в котором она объявлена. В некоторых случаях *уровень доступа* переменной может повлиять на ее область.  
  
 Для получения дополнительной информации см. [Scope in Visual Basic](scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Область на уровне блока или процедуры  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Предоставление переменной видимой только внутри блока  
  
- Поместите [оператор Dim](../../../language-reference/statements/dim-statement.md) для переменной между операторами объявления и завершения этого блока, например между `For` `Next` операторами и `For` цикла.  
  
     Ссылаться на переменную можно только внутри блока.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Предоставление переменной видимой только внутри процедуры  
  
- Поместите `Dim` оператор для переменной внутри процедуры, но вне любого блока (например, `With` блок... `End With` ).  
  
     Ссылаться на переменную можно только внутри процедуры, включая внутри любого блока, содержащегося в процедуре.  
  
## <a name="scope-at-module-or-namespace-level"></a>Область на уровне модуля или пространства имен  

 Для удобства *уровень модуля* единого термина применяется в равной степени к модулям, классам и структурам. Уровень доступа переменной уровня модуля определяет ее область. Пространство имен, содержащее модуль, класс или структуру, также влияет на область.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Чтобы сделать переменную видимой в пределах модуля, класса или структуры  
  
1. Поместите `Dim` оператор для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2. Включите в оператор ключевое слово [Private](../../../language-reference/modifiers/private.md) `Dim` .  
  
3. Можно ссылаться на переменную из любого места в модуле, классе или структуре, но не за ее пределами.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Как сделать переменную видимой во всем пространстве имен  
  
1. Поместите `Dim` оператор для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2. Включите в инструкцию ключевое слово [Friend](../../../language-reference/modifiers/friend.md) или [Public](../../../language-reference/modifiers/public.md) `Dim` .  
  
3. Можно ссылаться на переменную из любого места в пространстве имен, содержащем модуль, класс или структуру.  
  
## <a name="example"></a>Пример  

 В следующем примере объявляется переменная на уровне модуля и ограничивается ее видимость кодом внутри модуля.  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 В предыдущем примере все процедуры, определенные в модуле, `demonstrateScope` могут ссылаться на `String` переменную `strMsg` . При `usePrivateVariable` вызове процедуры она отображает содержимое строковой переменной `strMsg` в диалоговом окне.  
  
 После выполнения следующей изменения в предыдущем примере строковая переменная `strMsg` может называться кодом в любом месте пространства имен его объявления.  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 Чем более узкие области переменной, тем меньше возможностей вы случайно ссылаетесь на нее вместо другой переменной с тем же именем. Можно также избежать проблем, связанных с сопоставлением ссылок.  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  

 Чем короче область переменной, тем меньше вероятность того, что вредоносный код может неправильно использовать его.  
  
## <a name="see-also"></a>См. также

- [Область видимости в Visual Basic](scope.md)
- [Время существования в Visual Basic](lifetime.md)
- [Уровни доступа в Visual Basic](access-levels.md)
- [Переменные](../variables/index.md)
- [Объявление переменной](../variables/variable-declaration.md)
- [Оператор Dim](../../../language-reference/statements/dim-statement.md)
