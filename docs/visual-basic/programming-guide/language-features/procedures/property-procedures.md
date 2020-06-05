---
title: Процедуры свойств
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: cb5b0e12512e476b7c96bbfb19f8e4f470f6b498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363737"
---
# <a name="property-procedures-visual-basic"></a>Процедуры свойств (Visual Basic)

Процедура свойства — это серия Visual Basic инструкций, которые управляют пользовательским свойством модуля, класса или структуры. Процедуры свойств также называются свойствами *доступа к свойствам*.

Visual Basic предоставляет следующие процедуры свойств.

- `Get`Процедура возвращает значение свойства. Он вызывается при доступе к свойству в выражении.
- `Set`Процедура задает для свойства значение, включая ссылку на объект. Он вызывается при присвоении значения свойству.

Обычно процедуры свойств определяются парами с помощью `Get` `Set` инструкций и, но можно определить только одну процедуру, если свойство доступно только для чтения ([Инструкция Get](../../../language-reference/statements/get-statement.md)) или только для записи ([инструкция SET](../../../language-reference/statements/set-statement.md)).

Процедуру и можно опустить `Get` `Set` при использовании автоматического реализуемого свойства. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](./auto-implemented-properties.md).

Свойства можно определить в классах, структурах и модулях. Свойства по `Public` умолчанию. Это означает, что их можно вызывать из любого места в приложении, которое может получить доступ к контейнеру свойства.

Сравнение свойств и переменных см. [в разделе различия между свойствами и переменными в Visual Basic](differences-between-properties-and-variables.md).

## <a name="declaration-syntax"></a>Синтаксис объявления

Само свойство определяется блоком кода, заключенным в [Оператор Property](../../../language-reference/statements/property-statement.md) и `End Property` оператор. Внутри этого блока каждая процедура свойства отображается как внутренний блок, заключенный в оператор объявления ( `Get` или `Set` ) и в объявление сопоставления `End` .

Синтаксис объявления свойства и его процедур выглядит следующим образом:

```vb
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]
    [AccessLevel] Get
        ' Statements of the Get procedure.
        ' The following statement returns an expression as the property's value.
        Return Expression
    End Get
    [AccessLevel] Set[(ByVal NewValue As DataType)]
        ' Statements of the Set procedure.
        ' The following statement assigns newvalue as the property's value.
        LValue = NewValue
    End Set
End Property
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

В `Modifiers` можно указать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении, а также о том, доступно ли свойство только для чтения или только для записи. В `AccessLevel` `Get` `Set` процедуре или может быть любой уровень, который более четкий, чем уровень доступа, заданный для самого свойства. Дополнительные сведения см. в разделе [Оператор Property](../../../language-reference/statements/property-statement.md).

### <a name="data-type"></a>Тип данных

Тип данных свойства и основной уровень доступа определяются в `Property` инструкции, а не в процедурах свойства. Свойство может иметь только один тип данных. Например, нельзя определить свойство для хранения `Decimal` значения, но получить `Double` значение.

### <a name="access-level"></a>Уровень доступа

Однако можно определить основной уровень доступа для свойства и дополнительно ограничить уровень доступа в одной из его процедур свойств. Например, можно определить `Public` свойство, а затем определить `Private Set` процедуру. `Get`Процедура остается `Public` . Уровень доступа можно изменить только в одной из процедур свойства, и его можно сделать более узким, чем основной уровень доступа. Дополнительные сведения см. [в разделе инструкции. объявление свойства со смешанными уровнями доступа](how-to-declare-a-property-with-mixed-access-levels.md).

## <a name="parameter-declaration"></a>Объявление параметра

Каждый параметр объявляется так же, как и для [процедур подразделов](sub-procedures.md), за исключением того, что механизм передачи должен быть `ByVal` .

Для каждого параметра в списке параметров используется следующий синтаксис:

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

Если параметр является необязательным, необходимо также указать значение по умолчанию в составе объявления. Для указания значения по умолчанию используется следующий синтаксис:

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a>Значение свойства

В `Get` процедуре возвращаемое значение предоставляется вызывающему выражению как значение свойства.

В `Set` процедуре новое значение свойства передается в параметр `Set` инструкции. При явном объявлении параметра необходимо объявить его с тем же типом данных, что и свойство. Если параметр не объявлен, компилятор использует неявный параметр `Value` для представления нового значения, присваиваемого свойству.

## <a name="calling-syntax"></a>Синтаксис вызова

Процедура свойства вызывается неявно путем создания ссылки на свойство. Имя свойства используется так же, как имя переменной, за исключением того, что необходимо указать значения для всех аргументов, которые не являются необязательными, а список аргументов необходимо заключить в круглые скобки. Если аргументы не указаны, можно дополнительно опустить круглые скобки.

Для неявного вызова `Set` процедуры используется следующий синтаксис:

```vb
propertyname[(argumentlist)] = expression
```

Для неявного вызова `Get` процедуры используется следующий синтаксис:

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a>Иллюстрация объявления и вызова

Следующее свойство сохраняет полное имя как два составных имени: имя и фамилия. При чтении вызывающего кода `fullName` `Get` процедура объединяет два составных имени и возвращает полное имя. Когда вызывающий код присваивает новое полное имя, `Set` процедура попытается разбить ее на два составных имени. Если не удается найти пробел, он сохраняется как первое имя.

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

В следующем примере показаны типичные вызовы процедур свойств `fullName` :

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a>См. также раздел

- [Процедуры](index.md)
- [Процедуры функций](function-procedures.md)
- [Процедуры операторов](operator-procedures.md)
- [Параметры и аргументы процедуры](procedure-parameters-and-arguments.md)
- [Различия между свойствами и переменными в Visual Basic](differences-between-properties-and-variables.md)
- [Практическое руководство. Создание свойства](how-to-create-a-property.md)
- [Практическое руководство. Вызов процедуры свойства](how-to-call-a-property-procedure.md)
- [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](how-to-declare-and-call-a-default-property.md)
- [Практическое руководство. Запись значения в свойство](how-to-put-a-value-in-a-property.md)
- [Практическое руководство. Получение значения из свойства](how-to-get-a-value-from-a-property.md)
