---
description: Дополнительные сведения см. в статье как получить доступ к членам объекта (Visual Basic)
title: Практическое руководство. Доступ к членам объекта
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: b4aed213bbe520b7b7027acc146d0973f7273fd1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435529"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Практическое руководство. Доступ к членам объекта (Visual Basic)

При наличии переменной объекта, ссылающейся на объект, часто требуется работать с элементами этого объекта, такими как его методы, свойства, поля и события. Например, после создания нового <xref:System.Windows.Forms.Form> объекта может потребоваться задать его <xref:System.Windows.Forms.Control.Text%2A> свойство или вызвать его <xref:System.Windows.Forms.Control.Focus%2A> метод.

## <a name="accessing-members"></a>Доступ к членам

Доступ к членам объекта осуществляется через переменную, ссылающуюся на него.

#### <a name="to-access-members-of-an-object"></a>Получение доступа к членам объекта

- Используйте оператор доступа к членам ( `.` ) между именем объектной переменной и именем члена.

    ```vb
    currentText = newForm.Text
    ```

    Если член является [общим](../../../language-reference/modifiers/shared.md), для доступа к нему не требуется переменная.

## <a name="accessing-members-of-an-object-of-known-type"></a>Доступ к членам объекта известного типа

Если тип объекта известно во время компиляции, можно использовать *раннее связывание* для переменной, ссылающейся на нее.

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Доступ к членам объекта, тип которых вы узнаете во время компиляции

1. Объявите переменную объекта для типа объекта, который необходимо назначить переменной.

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    С помощью `Option Strict On` можно назначать только <xref:System.Windows.Forms.Form> объекты (или объекты типа, производного от <xref:System.Windows.Forms.Form> ) `extraForm` . Если вы определили класс или структуру с расширяющимся `CType` преобразованием в <xref:System.Windows.Forms.Form> , можно также присвоить этому классу или структуре значение `extraForm` .

2. Используйте оператор доступа к членам ( `.` ) между именем объектной переменной и именем члена.

    ```vb
    extraForm.Show()
    ```

    Можно получить доступ ко всем методам и свойствам, относящимся к <xref:System.Windows.Forms.Form> классу, независимо от значения `Option Strict` параметра.

## <a name="accessing-members-of-an-object-of-unknown-type"></a>Доступ к членам объекта неизвестного типа

Если тип объекта не знается во время компиляции, необходимо использовать *позднее связывание* для любой переменной, ссылающейся на нее.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Доступ к членам объекта, тип которых не знается во время компиляции

1. Объявите переменную объекта для [типа данных Object](../../../language-reference/data-types/object-data-type.md). (Объявление переменной как совпадает `Object` с ее объявлением как <xref:System.Object?displayProperty=nameWithType> .)

    ```vb
    Dim someControl As Object
    ```

    С помощью `Option Strict On` можно получить доступ только к тем элементам, которые определены в <xref:System.Object> классе.

2. Используйте оператор доступа к членам ( `.` ) между именем объектной переменной и именем члена.

    ```vb
    someControl.GetType()
    ```

    Чтобы иметь возможность доступа к членам любого объекта, назначаемого переменной объекта, необходимо задать `Option Strict Off` . При этом компилятор не может гарантировать, что данный элемент предоставляется объектом, назначаемым переменной. Если объект не предоставляет член, к которому вы пытаетесь получить доступ, <xref:System.MemberAccessException> возникает исключение.

## <a name="see-also"></a>См. также раздел

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Объектные переменные](object-variables.md)
- [Объявление объектной переменной](object-variable-declaration.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
