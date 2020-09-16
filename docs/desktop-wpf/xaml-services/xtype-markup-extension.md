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
ms.openlocfilehash: 00e6684f6ad1eb8d96f72f49bd5e0d211c8166c3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559074"
---
# <a name="xtype-markup-extension"></a>Расширение разметки x:Type

Предоставляет объект CLR <xref:System.Type> , который является базовым типом для указанного типа XAML.

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
|`prefix`|Необязательный элемент. Префикс, который сопоставляет пространство имен XAML, отличное от используемого по умолчанию. Указывать префикс часто необязательно. См. заметки.|
|`typeNameValue`|Обязательный. Имя типа, которое разрешается в текущее пространство имен XAML по умолчанию; или указанный сопоставленный префикс, если указан `prefix` аргумент.|

## <a name="remarks"></a>Примечания

`x:Type`Расширение разметки имеет аналогичную функцию `typeof()` оператору в C# или `GetType` операторе в Microsoft Visual Basic.

`x:Type`Расширение разметки предоставляет поведение преобразования из строки для свойств, которые принимают тип <xref:System.Type> . Входные данные являются типом XAML. Связь между входным типом XAML и выходным CLR заключается в том <xref:System.Type> , что выходные данные <xref:System.Type> являются <xref:System.Xaml.XamlType.UnderlyingType%2A> входными данными <xref:System.Xaml.XamlType> после поиска необходимых данных на <xref:System.Xaml.XamlType> основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver> службы, предоставляемой контекстом.

В службах .NET XAML обработка этого расширения разметки определяется <xref:System.Windows.Markup.TypeExtension> классом.

В определенных реализациях платформы некоторые свойства, принимающие в <xref:System.Type> качестве значения, могут принимать имя типа напрямую (строковое значение типа `Name` ). Однако реализация этого поведения является сложным сценарием. Примеры см. в разделе "Примечания об использовании WPF" ниже.

Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `x:Type`, присваивается в качестве значения <xref:System.Windows.Markup.TypeExtension.TypeName%2A> соответствующего класса расширения <xref:System.Windows.Markup.TypeExtension>. В контексте схемы XAML по умолчанию для служб XAML .NET, основанных на типах CLR, значение этого атрибута является либо либо <xref:System.Reflection.MemberInfo.Name%2A> типом требуемого типа, либо содержит <xref:System.Reflection.MemberInfo.Name%2A> префикс для сопоставления пространства имен XAML, не являющегося по умолчанию.

`x:Type`Расширение разметки можно использовать в синтаксисе объектного элемента. В этом случае <xref:System.Windows.Markup.TypeExtension.TypeName%2A> для правильной инициализации расширения требуется указать значение свойства.

`x:Type`Расширение разметки также можно использовать в качестве подробного атрибута, однако это не является типичным.`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

### <a name="default-xaml-namespace-and-type-mapping"></a>Сопоставление типов и пространства имен XAML по умолчанию

Пространство имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, необходимых для типичных сценариев XAML. Таким образом, часто можно избежать префиксов при ссылке на значения типа XAML. Может потребоваться сопоставить префикс, если вы ссылаетесь на тип из пользовательской сборки или для типов, существующих в сборке WPF, но из пространства имен CLR, которое не было сопоставлено с пространством имен XAML по умолчанию. Дополнительные сведения о префиксах, пространствах имен XAML и сопоставлении пространств имен CLR см. в разделе [пространства имен и сопоставление пространств имен XAML для WPF XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).

### <a name="type-properties-that-support-typename-as-string"></a>Свойства типа, поддерживающие TypeName в виде строки

WPF поддерживает приемы, позволяющие указывать значения некоторых свойств типа <xref:System.Type> без `x:Type` использования расширения разметки. Вместо этого можно указать значение в виде строки с именем типа. Примеры: <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> и <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType> . Поддержка этого поведения не предоставляется ни с помощью преобразователей типов, ни из расширений разметки. Вместо этого это поведение, реализованное с помощью <xref:System.Windows.FrameworkElementFactory> .

Silverlight поддерживает аналогичное соглашение. На самом деле Silverlight в настоящее время не поддерживает `{x:Type}` поддержку языка XAML и не принимает `{x:Type}` использование за пределами нескольких обстоятельств, предназначенных для поддержки миграции XAML WPF-Silverlight. Таким образом, поведение типа "имя-строка" встроено во все вычисления собственного свойства Silverlight, где <xref:System.Type> — это значение.

## <a name="xaml-2009"></a>XAML 2009

XAML 2009 обеспечивает дополнительную поддержку для универсальных типов и изменяет поведение функций `x:TypeArguments` и `x:Type` для предоставления этой поддержки.

- `x:TypeArguments` и связанный элемент объекта для создания экземпляра универсального объекта может находиться в элементах, отличных от корневого. Дополнительные сведения см. в разделе "XAML 2009" [директивы x:TypeArguments](xtypearguments-directive.md).

- XAML 2009 поддерживает синтаксис для указания ограничения универсального типа в разметке. Это можно использовать `x:TypeArguments` в, by `x:Type` или двух функциях в сочетании.

- Реализация XAML в WPF при обработке XAML 2009 для загрузки также добавляет эту возможность в поведение неявного преобразования типов для определенных свойств платформы, использующих тип <xref:System.Type> .

В WPF можно использовать функции XAML 2009, но только для свободного XAML (XAML, не компилируемого разметкой). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Style>
- [Стилизация и использование шаблонов](../fundamentals/styles-templates-overview.md)
- [Обзор XAML (WPF)](../fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
