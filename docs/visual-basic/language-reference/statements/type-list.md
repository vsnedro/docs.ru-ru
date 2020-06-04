---
title: Type List
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 7e22ad6e32ec13f081391e1d47a80df8b1e65063
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412992"
---
# <a name="type-list-visual-basic"></a>Список типов (Visual Basic)

Задает *Параметры типа* для *универсального* программного элемента. Несколько параметров разделяются запятыми. Ниже приведен синтаксис для одного параметра типа.

## <a name="syntax"></a>Синтаксис

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>Компоненты

|Термин|Определение|
|---|---|
|`genericmodifier`|Необязательный элемент. Может использоваться только в универсальных интерфейсах и делегатах. Ковариантность типа можно объявить с помощью ключевого слова [out](../modifiers/out-generic-modifier.md) или контравариантного с помощью ключевого слова [in](../modifiers/in-generic-modifier.md) . См. раздел [Ковариация и контрвариация](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Обязательный. Имя параметра типа. Это заполнитель, заменяемый определенным типом, предоставленным соответствующим аргументом типа.|
|`constraintlist`|Необязательный элемент. Список требований, ограничивающих тип данных, который может быть представлен для `typename` . При наличии нескольких ограничений заключите их в фигурные скобки ( `{ }` ) и разделите их запятыми. Список ограничений необходимо ввести с помощью ключевого слова [as](as-clause.md) . Используется `As` только один раз в начале списка.|

## <a name="remarks"></a>Комментарии

Каждый универсальный программный элемент должен принимать по крайней мере один параметр типа. Параметр типа — это заполнитель для определенного типа ( *сконструированного элемента*), который клиентский код указывает при создании экземпляра универсального типа. Можно определить универсальный класс, структуру, интерфейс, процедуру или делегат.

Дополнительные сведения о том, когда следует определять универсальный тип, см. [в разделе Универсальные типы в Visual Basic](../../programming-guide/language-features/data-types/generic-types.md). Дополнительные сведения об именах параметров типов см. в разделе [Имена объявленных элементов](../../programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Правила

- **Скобки.** Если вы представите список параметров типа, необходимо заключить его в круглые скобки и ввести в список ключевое слово [of](of-clause.md) . Используется `Of` только один раз в начале списка.

- **Учитывая.** Список *ограничений* для параметра типа может включать в себя следующие элементы в любом сочетании:

  - Любое количество интерфейсов. Указанный тип должен реализовывать каждый интерфейс в этом списке.

  - Не более одного класса. Указанный тип должен наследоваться от этого класса.

  - Ключевое слово `New`. Предоставленный тип должен предоставлять конструктор без параметров, к которому имеет доступ универсальный тип. Это полезно, если параметр типа ограничивается одним или несколькими интерфейсами. Тип, реализующий интерфейсы, не обязательно предоставляет конструктор, и в зависимости от уровня доступа конструктора код в универсальном типе может не иметь возможности получить к нему доступ.

  - `Class`Ключевое слово или `Structure` ключевое слово. `Class`Ключевое слово ограничивает параметр универсального типа, требуя, чтобы любой передаваемый аргумент типа был ссылочным типом, например строкой, массивом или делегатом, или объектом, созданным из класса. `Structure`Ключевое слово ограничивает параметр универсального типа, требуя, чтобы любой передаваемый аргумент типа был типом значения, например структурой, перечислением или простым типом данных. Нельзя включать `Class` и `Structure` в, и в одном и том же `constraintlist` .

  Указанный тип должен отвечать всем требованиям, включенным в `constraintlist` .

  Ограничения для каждого параметра типа не зависят от ограничений для других параметров типа.

## <a name="behavior"></a>Поведение

- **Подстановка во время компиляции.** При создании сконструированного типа на основе универсального программного элемента вы предоставляете определенный тип для каждого параметра типа. Компилятор Visual Basic замещает указанный тип для каждого вхождения `typename` в пределах универсального элемента.

- **Отсутствие ограничений.** Если не указать какие-либо ограничения на параметр типа, код будет ограничен операциями и элементами, поддерживаемыми [типом данных Object](../data-types/object-data-type.md) для этого параметра типа.

## <a name="example"></a>Пример

В следующем примере показано определение каркаса универсального класса Dictionary, включая скелет функции для добавления новой записи в словарь.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Пример

Поскольку `dictionary` является универсальным, код, который использует его, может создавать разнообразные объекты, каждый из которых имеет одинаковые функциональные возможности, но работает с другим типом данных. В следующем примере показана строка кода, создающая `dictionary` объект с `String` записями и `Integer` ключами.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Пример

В следующем примере показано эквивалентное определение скелета, созданное в предыдущем примере.

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>См. также раздел

- [Окна](of-clause.md)
- [Оператор New](../operators/new-operator.md)
- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Object Data Type](../data-types/object-data-type.md)
- [Оператор Function](function-statement.md)
- [Оператор Structure](structure-statement.md)
- [Оператор Sub](sub-statement.md)
- [Практическое руководство. Использование универсального класса](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Ковариация и контрвариантность](../../programming-guide/concepts/covariance-contravariance/index.md)
- [В](../modifiers/in-generic-modifier.md)
- [Заполняет](../modifiers/out-generic-modifier.md)
