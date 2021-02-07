---
description: 'Дополнительные сведения: Оператор Property'
title: Property Statement
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 95f2ac1f993fc8698d2033dfe50d925cd55a7dc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741397"
---
# <a name="property-statement"></a>Property Statement

Объявляет имя свойства и процедуры свойства, используемые для хранения и извлечения значения свойства.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a>Компоненты

- `attributelist`

  Необязательный элемент. Список атрибутов, применяемых к этому свойству `Get` или `Set` процедуре. См. [список атрибутов](attribute-list.md).

- `Default`

  Необязательный элемент. Указывает, что это свойство является свойством по умолчанию для класса или структуры, в которой он определен. Свойства по умолчанию должны принимать параметры и могут быть заданы и получены без указания имени свойства. Если объявить свойство как `Default` , нельзя использовать `Private` для свойства или для любой из его процедур свойств.

- `accessmodifier`

  Необязательно для инструкции и не более чем с `Property` одним из `Get` `Set` операторов и. Может принимать следующие значения:

  - [Общедоступная](../modifiers/public.md)

  - [Защищенный](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Частная](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Частный защищенный](../modifiers/private-protected.md)

  См. раздел [уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `propertymodifiers`

  Необязательный элемент. Может принимать следующие значения:

  - [Перегрузки](../modifiers/overloads.md)

  - [Переопределения](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Необязательный элемент. См. раздел [Shared](../modifiers/shared.md).

- `Shadows`

  Необязательный элемент. См. раздел [Shadows](../modifiers/shadows.md).

- `ReadOnly`

  Необязательный элемент. См. раздел [ReadOnly](../modifiers/readonly.md).

- `WriteOnly`

  Необязательный элемент. См. раздел [WriteOnly](../modifiers/writeonly.md).

- `Iterator`

  Необязательный элемент. См. [итератор](../modifiers/iterator.md).

- `name`

  Обязательный элемент. Имя свойства. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `parameterlist`

  Необязательный элемент. Список имен локальных переменных, представляющих параметры этого свойства, и возможные дополнительные параметры `Set` процедуры. См. [список параметров](parameter-list.md).

- `returntype`

  Обязательный `Option Strict` , если имеет значение `On` . Тип данных значения, возвращаемого этим свойством.

- `Implements`

  Необязательный элемент. Указывает, что это свойство реализует одно или несколько свойств, каждое из которых определено в интерфейсе, реализуемом классом или структурой этого свойства. См. [инструкцию Implements](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых свойств.

  `implementedproperty [ , implementedproperty ... ]`

  Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.

  `interface.definedname`

  |Отделение|Описание|
  |---|---|
  |`interface`|Обязательный элемент. Имя интерфейса, реализованного в классе или структуре этого свойства.|
  |`definedname`|Обязательный элемент. Имя, по которому определено свойство `interface` .|

- `Get`

  Необязательный элемент. Требуется, если свойство помечено как `ReadOnly` . Запускает `Get` процедуру свойства, которая используется для возврата значения свойства.  `Get`Инструкция не используется с [автоматической реализацией свойств](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `statements`

  Необязательный элемент. Блок инструкций для выполнения в `Get` `Set` процедуре или.

- `End Get`

  Завершает `Get` процедуру свойства.

- `Set`

  Необязательный элемент. Требуется, если свойство помечено как `WriteOnly` . Запускает `Set` процедуру свойства, используемую для хранения значения свойства.  `Set`Инструкция не используется с [автоматической реализацией свойств](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `End Set`

  Завершает `Set` процедуру свойства.

- `End Property`

  Завершает определение этого свойства.

## <a name="remarks"></a>Remarks

`Property`Оператор вводит объявление свойства. Свойство может иметь `Get` процедуру (только для чтения), `Set` процедуру (только для записи) или и то, и другое (чтение и запись). Процедуру и можно опустить `Get` `Set` при использовании автоматического реализуемого свойства. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

Можно использовать `Property` только на уровне класса. Это означает, что *контекст объявления* для свойства должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

По умолчанию свойства используют общий доступ. Можно настроить уровень доступа свойства с помощью модификатора доступа в `Property` инструкции, и при необходимости можно настроить одну из его процедур свойств на более ограниченный уровень доступа.

Visual Basic передает параметр в `Set` процедуру во время назначения свойств. Если параметр для не указан `Set` , в интегрированной среде разработки (IDE) используется неявный параметр с именем `value` . Этот параметр содержит значение, присваиваемое свойству. Обычно это значение сохраняется в закрытой локальной переменной и возвращается при каждом `Get` вызове процедуры.

## <a name="rules"></a>Правила

- **Уровни смешанного доступа.** При определении свойства для чтения и записи можно дополнительно указать другой уровень доступа для `Get` `Set` процедуры или, но не для обоих. В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства. Например, если свойство объявлено `Friend` , можно объявить `Set` процедуру `Private` , но не `Public` .

  При определении `ReadOnly` `WriteOnly` свойства или процедура с одним свойством ( `Get` или `Set` соответственно) представляет все свойство. Для такой процедуры нельзя объявить другой уровень доступа, поскольку в этом случае для свойства будет задано два уровня доступа.

- **Тип возвращаемого значения.** `Property`Оператор может объявить тип данных возвращаемого значения. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.

  Если не указать `returntype` , свойство возвращает значение `Object` .

- **Реализации.** Если это свойство использует `Implements` ключевое слово, содержащий класс или структуру должны иметь `Implements` оператор, непосредственно следующий за `Class` `Structure` оператором или. `Implements`Инструкция должна включать каждый интерфейс, указанный в `implementslist` . Однако имя, по которому интерфейс определяет `Property` (in `definedname` ), не обязательно должно совпадать с именем этого свойства (в `name` ).

## <a name="behavior"></a>Поведение

- **Возврат из процедуры свойства.** Когда `Get` процедура или `Set` возвращает в вызывающий код, выполнение продолжится с оператора, следующего за оператором, вызвавшим ее.

  `Exit Property`Операторы и `Return` вызывают немедленный выход из процедуры свойства. Любое количество `Exit Property` инструкций и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Property` `Return` операторы и.

- **Возвращаемое значение.** Чтобы вернуть значение из `Get` процедуры, можно либо присвоить значение имени свойства, либо включить его в `Return` инструкцию. В следующем примере возвращаемое значение присваивается имени свойства `quoteForTheDay` , а затем используется `Exit Property` оператор для возврата.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  Если вы используете `Exit Property` без присвоения значения `name` , `Get` процедура возвращает значение по умолчанию для типа данных свойства.

  `Return`Инструкция в то же время присваивает `Get` возвращаемое значение процедуры и завершает процедуру. В следующем примере приведена иллюстрация этого.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>Пример

В следующем примере объявляется свойство в классе.

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>См. также

- [Автоматически реализуемые свойства](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
- [Оператор Get](get-statement.md)
- [Инструкция SET](set-statement.md)
- [Список параметров](parameter-list.md)
- [Default](../modifiers/default.md)
