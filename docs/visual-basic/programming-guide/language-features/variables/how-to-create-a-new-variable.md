---
description: Дополнительные сведения см. в статье как создать новую переменную (Visual Basic).
title: Практическое руководство. Создание новой переменной
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: b473a247bc5b4d9c1d65f4721ecba3621b232e27
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481965"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Практическое руководство. Создание новой переменной (Visual Basic)

Переменная создается с помощью [оператора Dim](../../../language-reference/statements/dim-statement.md).

### <a name="to-create-a-new-variable"></a>Создание новой переменной

1. Объявите переменную в `Dim` операторе.

    ```vb
    Dim newCustomer
    ```

2. Включите спецификации для характеристик переменной, например [Private](../../../language-reference/modifiers/private.md), [static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)или [WithEvents](../../../language-reference/modifiers/withevents.md). Дополнительные сведения см. в разделе [Характеристики объявленных элементов](../declared-elements/declared-element-characteristics.md).

    ```vb
    Public Static newCustomer
    ```

    `Dim`Ключевое слово не требуется, если в объявлении используются другие ключевые слова.

3. Используйте спецификации с именем переменной, которое должно соответствовать правилам и соглашениям Visual Basic. Дополнительные сведения см. в разделе [Имена объявленных элементов](../declared-elements/declared-element-names.md).

    ```vb
    Public Static newCustomer
    ```

4. Чтобы указать тип данных переменной, используйте имя с предложением [as](../../../language-reference/statements/as-clause.md) .

    ```vb
    Public Static newCustomer As Customer
    ```

    Если тип данных не указан, используется значение по умолчанию: `Object` .

5. Следуйте `As` предложению со знаком равенства ( `=` ) и выполните знак равенства с начальным значением переменной.

    Visual Basic назначает указанное значение переменной при каждом выполнении `Dim` инструкции. Если не указать начальное значение, Visual Basic присваивает начальное значение по умолчанию для типа данных переменной при первом входе в код, содержащий `Dim` инструкцию.

    Если переменная является ссылочным типом, можно создать экземпляр его класса, включив в предложение ключевое слово [New operator](../../../language-reference/operators/new-operator.md) `As` . Если не используется `New` , начальное значение переменной равно [Nothing](../../../language-reference/nothing.md).

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>См. также раздел

- [Переменные](index.md)
- [Объявление переменной](variable-declaration.md)
- [Declared Element Names](../declared-elements/declared-element-names.md)
- [Характеристики объявленных элементов](../declared-elements/declared-element-characteristics.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)
- [Операторы](../../../language-reference/statements/index.md)
- [Вывод локального типа](local-type-inference.md)
- [Оператор Option Infer](../../../language-reference/statements/option-infer-statement.md)
