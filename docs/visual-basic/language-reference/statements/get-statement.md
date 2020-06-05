---
title: Оператор Get
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 31936fb2c8f658203a43702a2b5fa4ee2481beb5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404606"
---
# <a name="get-statement"></a>Оператор Get
Объявляет `Get` процедуру свойства, используемую для получения значения свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`attributelist`|Необязательный элемент. См. [список атрибутов](attribute-list.md).|  
|`accessmodifier`|Необязательно для одного из `Get` `Set` операторов и в этом свойстве. Может принимать следующие значения:<br /><br /> -   [От](../modifiers/protected.md)<br />-   [Объявление](../modifiers/friend.md)<br />-   [Личному](../modifiers/private.md)<br />-   `Protected Friend`<br /><br /> См. раздел [уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Необязательный элемент. Одна или несколько инструкций, выполняемых при `Get` вызове процедуры свойства.|  
|`End Get`|Обязательный. Завершает определение `Get` процедуры свойства.|  
  
## <a name="remarks"></a>Комментарии  
 Каждое свойство должно иметь `Get` процедуру свойства, если только свойство не помечено как `WriteOnly` . `Get`Процедура используется для возврата текущего значения свойства.  
  
 Visual Basic автоматически вызывает процедуру свойства, `Get` когда выражение запрашивает значение свойства.  
  
 Текст объявления свойства может содержать только `Get` процедуры свойства и `Set` между [оператором Property](property-statement.md) и `End Property` оператором. Он не может хранить ничего, Кроме этих процедур. В частности, он не может хранить текущее значение свойства. Это значение необходимо хранить за пределами свойства, так как при хранении в любой из процедур свойств другая процедура свойства не может получить к ней доступ. Обычным подходом является сохранение значения в [закрытой](../modifiers/private.md) переменной, объявленной на том же уровне, что и свойство. Необходимо определить `Get` процедуру внутри свойства, к которому она применяется.  
  
 `Get`Процедура по умолчанию имеет уровень доступа содержащего его свойства, если только не используется `accessmodifier` в `Get` инструкции.  
  
## <a name="rules"></a>Правила  
  
- **Уровни смешанного доступа.** При определении свойства для чтения и записи можно дополнительно указать другой уровень доступа для `Get` `Set` процедуры или, но не для обоих. В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства. Например, если свойство объявлено `Friend` , можно объявить `Get` процедуру `Private` , но не `Public` .  
  
     При определении `ReadOnly` свойства `Get` процедура представляет все свойство. Нельзя объявить другой уровень доступа для `Get` , так как для свойства будет задано два уровня доступа.  
  
- **Тип возвращаемого значения.** [Оператор Property](property-statement.md) может объявлять тип данных возвращаемого значения. `Get`Процедура автоматически возвращает этот тип данных. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
     Если `Property` инструкция не указывает `returntype` , процедура возвращает `Object` .  
  
## <a name="behavior"></a>Поведение  
  
- **Возврат из процедуры.** Когда `Get` процедура возвращается в вызывающий код, выполнение продолжится в операторе, который запросил значение свойства.  
  
     `Get`процедуры свойств могут возвращать значение с помощью [оператора return](return-statement.md) или путем назначения возвращаемого значения имени свойства. Дополнительные сведения см. в разделе "возвращаемое значение" в [операторе Function](function-statement.md).  
  
     `Exit Property`Операторы и `Return` вызывают немедленный выход из процедуры свойства. Любое количество `Exit Property` инструкций и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Property` `Return` операторы и.  
  
- **Возвращаемое значение.** Чтобы вернуть значение из `Get` процедуры, можно либо присвоить значение имени свойства, либо включить его в [оператор return](return-statement.md). `Return`Инструкция одновременно присваивает `Get` возвращаемое значение процедуры и завершает процедуру.  
  
     Если вы используете `Exit Property` без присвоения значения имени свойства, `Get` процедура возвращает значение по умолчанию для типа данных свойства. Дополнительные сведения см. в разделе "возвращаемое значение" в [операторе Function](function-statement.md).  
  
     В следующем примере показаны два способа, которыми свойство только для чтения `quoteForTheDay` может возвращать значение, удерживаемое в закрытой переменной `quoteValue` .  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `Get` для возврата значения свойства.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>См. также раздел

- [Инструкция SET](set-statement.md)
- [Property Statement](property-statement.md)
- [Оператор Exit](exit-statement.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
- [Пошаговое руководство. Определение классов](../../programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
