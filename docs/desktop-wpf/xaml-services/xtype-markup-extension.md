---
title: Расширение разметки x:Type
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432638"
---
# <a name="xtype-markup-extension"></a>Расширение разметки x:Type

Поставляет объект <xref:System.Type> CLR, который является базовым типом для указанного типа XAML.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`prefix`|Необязательный параметр. Приставка, на которой отображается непо умолчанию пространство имен XAML. Указывать префикс часто не требуется. См. заметки.|
|`typeNameValue`|Обязательный элемент. Имя типа, разрешимое в текущем пространстве имен XAML по умолчанию; или указанная отображаемые префиксы, если `prefix` поставляется.|

## <a name="remarks"></a>Примечания

Расширение `x:Type` разметки имеет аналогичную функцию `typeof()` оператора `GetType` в СЗ или оператора в Microsoft Visual Basic.

Расширение `x:Type` разметки обеспечивает поведение преобразования из строки <xref:System.Type>для свойств, которые принимают тип. Ввод — это тип XAML. Взаимосвязь между типом ввода XAML <xref:System.Type> и выходом <xref:System.Type> CLR заключается в том, что выходом <xref:System.Xaml.XamlType.UnderlyingType%2A> является входный, <xref:System.Xaml.XamlType>после поиска необходимого <xref:System.Xaml.XamlType> контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver> службы, предоставляемой контекстом.

В службах .NET XAML обработка этого расширения <xref:System.Windows.Markup.TypeExtension> разметки определяется классом.

В определенных реализации фреймворка некоторые свойства, которые принимаются <xref:System.Type> в качестве `Name`значения, могут принимать имя типа напрямую (значение строки типа). Однако реализация такого поведения является сложным сценарием. Например, смотрите нижеследующий раздел "Примечания к использованию WPF".

Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `x:Type`, присваивается в качестве значения <xref:System.Windows.Markup.TypeExtension.TypeName%2A> соответствующего класса расширения <xref:System.Windows.Markup.TypeExtension>. В контексте схемы XAML по умолчанию для .NET XAML Services, основанной на <xref:System.Reflection.MemberInfo.Name%2A> типах CLR, значение <xref:System.Reflection.MemberInfo.Name%2A> этого атрибута является либо желаемым типом, либо содержит, что предшествует префиксу для непо умолчанию отображения пространства имен XAML.

Расширение `x:Type` разметки может быть использовано в синтаксисе элемента объекта. В этом случае для правильной <xref:System.Windows.Markup.TypeExtension.TypeName%2A> инициализации расширения требуется указание стоимости имущества.

Расширение `x:Type` разметки также может быть использовано в качестве многословного атрибута; однако это использование не является типичным:`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

### <a name="default-xaml-namespace-and-type-mapping"></a>По умолчанию XAML Namespace и тип овоей картографирования

Пространство имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, необходимых для типичных сценариев XAML; поэтому часто можно избежать префиксов при ссылках на значения типа XAML. Возможно, вам потребуется сопоставить префикс, если вы ссылаетесь на тип из пользовательской сборки или на типы, которые существуют в сборке WPF, но относятся к пространству имен CLR, которое не было отображено в пространстве имен XAML по умолчанию. Для получения дополнительной информации о префиксах, пространствах имен XAML и картографировании названий CLR [см.](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)

### <a name="type-properties-that-support-typename-as-string"></a>Введите свойства, которые поддерживают typename-as-String

WPF поддерживает методы, позволяющие указывать <xref:System.Type> значение некоторых свойств типа без необходимости использования расширения `x:Type` разметки. Вместо этого можно указать значение в виде строки, которая называет тип. Примеры этого <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>и . Поддержка такого поведения не обеспечивается ни через конвертеры типа, ни расширения разметки. Вместо этого, это поведение отсрочки <xref:System.Windows.FrameworkElementFactory>реализованы через .

Silverlight поддерживает аналогичную конвенцию. На самом деле, Silverlight `{x:Type}` в настоящее время не поддерживает `{x:Type}` поддержку языка XAML и не принимает обычаи за пределами нескольких обстоятельств, которые предназначены для поддержки миграции WPF-Silverlight XAML. Таким образом, типовое имя как строка поведение встроено во <xref:System.Type> все Silverlight родной оценки собственности, где это значение.

## <a name="xaml-2009"></a>XAML 2009

XAML 2009 обеспечивает дополнительную поддержку для генерических типов и изменяет функциональное поведение `x:TypeArguments` и `x:Type` обеспечивает эту поддержку.

- `x:TypeArguments`и связанный элемент объекта для мгновенного общего объекта может быть на элементах, не связанных с корнем. Для получения дополнительной информации см. [x:TypeArguments Directive](xtypearguments-directive.md)

- XAML 2009 поддерживает синтаксис для указания ограничения общего типа в разметке. Это может быть `x:TypeArguments`использовано, , `x:Type`или двумя функциями в сочетании.

- Внедрение WPF XAML при обработке XAML 2009 для загрузки также добавляет эту <xref:System.Type>возможность к неявному поведению преобразования типа для определенных свойств фреймворка, которые используют тип.

В WPF, вы можете использовать функции XAML 2009, но только для свободного XAML (XAML, который не разметка-компилируется). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Style>
- [Стилизация и использование шаблонов](../fundamentals/styles-templates-overview.md)
- [Обзор XAML (WPF)](../fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
