---
description: Дополнительные сведения см. в статье как определить тип, на который ссылается объектная переменная (Visual Basic)
title: Практическое руководство. Определение типа, на который указывает объектная переменная
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 699a8c5c075fc923a61a66f617c255f193cd8797
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481926"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Практическое руководство. Определение типа, на который указывает объектная переменная (Visual Basic)

Объектная переменная содержит указатель на данные, которые хранятся в других местах. Тип этих данных может изменяться во время выполнения. В любой момент можно использовать <xref:System.Type.GetTypeCode%2A> метод для определения текущего типа времени выполнения или [оператор typeof](../../../language-reference/operators/typeof-operator.md) , чтобы определить, совместим ли текущий тип времени выполнения с указанным типом.

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Определение точного типа объектной переменной, на которую в настоящее время ссылается

1. В объектной переменной вызовите <xref:System.Object.GetType%2A> метод, чтобы получить <xref:System.Type?displayProperty=nameWithType> объект.

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. В <xref:System.Type?displayProperty=nameWithType> классе вызовите метод Shared, <xref:System.Type.GetTypeCode%2A> чтобы получить <xref:System.TypeCode> значение перечисления для типа объекта.

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    Можно проверить <xref:System.TypeCode> значение перечисления в отношении любого интересующего его члена, например `Double` .

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Определение, совместима ли тип объектной переменной с указанным типом

- Используйте `TypeOf` оператор в сочетании с [оператором is](../../../language-reference/operators/is-operator.md) для проверки объекта с помощью выражения. `TypeOf` .. `Is`

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    `TypeOf`Выражение... `Is` возвращает значение, `True` Если тип времени выполнения объекта совместим с указанным типом.

    Критерий совместимости зависит от того, является ли указанный тип классом, структурой или интерфейсом. Как правило, типы являются совместимыми, если объект имеет тот же тип, что и, наследует от или реализует указанный тип. Дополнительные сведения см. в разделе [оператор typeof](../../../language-reference/operators/typeof-operator.md).

## <a name="compile-the-code"></a>Компиляция кода

Обратите внимание, что указанный тип не может быть переменной или выражением. Это должно быть имя определенного типа, например класса, структуры или интерфейса. Сюда входят встроенные типы, такие как `Integer` и `String` .

## <a name="see-also"></a>См. также раздел

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Объектные переменные](object-variables.md)
- [Значения объектных переменных](object-variable-values.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
