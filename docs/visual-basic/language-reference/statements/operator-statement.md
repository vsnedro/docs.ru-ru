---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: f9e6ffe5a49715592399321ab471d73826e05d8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404399"
---
# <a name="operator-statement"></a>Operator Statement

Объявляет символ оператора, операнды и код, определяющие процедуру оператора для класса или структуры.

## <a name="syntax"></a>Синтаксис

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a>Компоненты

`attrlist`  
Необязательный элемент. См. [список атрибутов](attribute-list.md).

`Public`  
Обязательный. Указывает, что эта процедура оператора имеет [открытый](../modifiers/public.md) доступ.

`Overloads`  
Необязательный элемент. См. раздел [Overloads](../modifiers/overloads.md).

`Shared`  
Обязательный. Указывает, что эта процедура оператора является [общей](../modifiers/shared.md) процедурой.

`Shadows`  
Необязательный элемент. См. раздел [Shadows](../modifiers/shadows.md).

`Widening`  
Требуется для оператора преобразования, если не указано значение `Narrowing` . Указывает, что эта процедура оператора определяет [расширяющее](../modifiers/widening.md) преобразование. См. раздел "расширяющие и сужающие преобразования" на этой странице справки.

`Narrowing`  
Требуется для оператора преобразования, если не указано значение `Widening` . Указывает, что эта процедура оператора определяет [понижающие](../modifiers/narrowing.md) преобразования. См. раздел "расширяющие и сужающие преобразования" на этой странице справки.

`operatorsymbol`  
Обязательный. Символ или идентификатор оператора, определяемого данной процедурой оператора.

`operand1`  
Обязательный. Имя и тип одного операнда унарного оператора (включая оператор преобразования) или левого операнда бинарного оператора.

`operand2`  
Требуется для бинарных операторов. Имя и тип правого операнда бинарного оператора.

`operand1`и `operand2` имеют следующий синтаксис и части:

`[ ByVal ] operandname [ As operandtype ]`

|Часть|Описание|
|----------|-----------------|
|`ByVal`|Необязательно, но механизм передачи должен быть [ByVal](../modifiers/byval.md).|
|`operandname`|Обязательный. Имя переменной, представляющей этот операнд. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`operandtype`|Необязательный `Option Strict` , если не имеет `On` . Тип данных этого операнда.|

`type`  
Необязательный `Option Strict` , если не имеет `On` . Тип данных значения, возвращаемого процедурой оператора.

`statements`  
Необязательный элемент. Блок инструкций, выполняемых процедурой оператора.

`returnvalue`  
Обязательный. Значение, возвращаемое процедурой оператора в вызывающий код.

`End` `Operator`  
Обязательный. Завершает определение этой процедуры оператора.

## <a name="remarks"></a>Комментарии

Можно использовать `Operator` только в классе или структуре. Это означает, что *контекст объявления* для оператора не может быть исходным файлом, пространством имен, модулем, интерфейсом, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

Все операторы должны быть `Public Shared` . Нельзя указывать `ByRef` , `Optional` или `ParamArray` для любого из операндов.

Нельзя использовать символ оператора или идентификатор для хранения возвращаемого значения. Необходимо использовать `Return` инструкцию, и она должна указывать значение. Любое количество `Return` инструкций может находиться в любом месте процедуры.

Определение оператора таким образом называется *перегрузкой операторов*независимо от того, используется `Overloads` ключевое слово или нет. В приведенной ниже таблице перечислены операторы, которые можно определить.

|Тип|Операторы|
|----------|---------------|
|Унарный|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Двоичный|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Преобразование (унарный)|`CType`|

Обратите внимание, что `=` оператор в списке binary является оператором сравнения, а не оператором присваивания.

При определении необходимо `CType` указать либо `Widening` `Narrowing` .

## <a name="matched-pairs"></a>Парные пары

Необходимо определить определенные операторы в качестве совпадающих пар. При определении любого из этих двух операторов такой пары необходимо определить и другое. Сопоставленные пары являются следующими:

- `=` и `<>`

- `>` и `<`

- `>=` и `<=`

- `IsTrue` и `IsFalse`

## <a name="data-type-restrictions"></a>Ограничения типов данных

Каждый определяемый оператор должен содержать класс или структуру, в которых он определен. Это означает, что класс или структура должны выглядеть как тип данных следующего:

- Операнд унарного оператора.

- По крайней мере один из операндов бинарного оператора.

- Либо операнд, либо тип возвращаемого значения оператора преобразования.

 Некоторые операторы имеют дополнительные ограничения по типам данных, как показано ниже.

- При определении `IsTrue` `IsFalse` операторов and они должны возвращать `Boolean` тип.

- При определении `<<` `>>` операторов and они должны указывать `Integer` тип для `operandtype` `operand2` .

Тип возвращаемого значения не должен соответствовать типу любого из операндов. Например, оператор сравнения, например или, `=` `<>` может возвращать значение, `Boolean` даже если ни один из операндов не равен `Boolean` .

## <a name="logical-and-bitwise-operators"></a>Логические и побитовые операторы

`And`Операторы, `Or` , `Not` и `Xor` могут выполнять логические или побитовые операции в Visual Basic. Однако при определении одного из этих операторов для класса или структуры можно определить только его побитовую операцию.

Оператор нельзя определить `AndAlso` непосредственно с помощью `Operator` оператора. Тем не менее, можно использовать, `AndAlso` если выполнены следующие условия.

- Вы определили `And` те же типы операндов, которые вы хотите использовать для `AndAlso` .

- Определение `And` возвращает тот же тип, что и класс или структура, в которой он определен.

- Вы определили `IsFalse` оператор для класса или структуры, в которой вы определили `And` .

Аналогичным образом можно использовать, `OrElse` Если вы определили в `Or` одних и тех же операндах с типом возвращаемого значения класса или структуры и определили `IsTrue` в классе или структуре.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

*Расширяющее преобразование* всегда выполняется успешно во время выполнения, в то время как *понижающие преобразования* могут завершиться ошибкой во время выполнения. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

Если объявляется процедура преобразования `Widening` , код процедуры не должен создавать ошибок. Это означает следующее:

- Он должен всегда возвращать допустимое значение типа `type` .

- Он должен поддерживать все возможные исключения и другие условия возникновения ошибок.

- Она должна поддерживать любые ошибки, возвращаемые из всех процедур, которые она вызывает.

Если существует вероятность того, что процедура преобразования может быть невозможной или она может вызвать необработанное исключение, необходимо объявить ее как `Narrowing` .

## <a name="example"></a>Пример

В следующем примере кода инструкция используется `Operator` для определения структуры структуры, которая включает в себя процедуры операторов для `And` операторов,, `Or` `IsFalse` и `IsTrue` . `And`и `Or` каждый из них принимает два операнда типа `abc` и типа возвращаемого значения `abc` . `IsFalse``IsTrue`каждый из них принимает один операнд типа `abc` и возвращает значение `Boolean` . Эти определения позволяют вызывающему коду использовать `And` , `AndAlso` , `Or` и `OrElse` с операндами типа `abc` .

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>См. также раздел

- [Оператор IsFalse](../operators/isfalse-operator.md)
- [Оператор IsTrue](../operators/istrue-operator.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Процедуры операторов](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Практическое руководство. Определение оператора](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Практическое руководство. Вызов процедуры оператора](../../programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [Практическое руководство. Использование класса, в котором определяются операторы](../../programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
