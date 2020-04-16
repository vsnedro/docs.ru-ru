---
title: Директива x:TypeArguments
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432632"
---
# <a name="xtypearguments-directive"></a>Директива x:TypeArguments

Передает ограничивающие аргументы типа общего для конструктора общего типа.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`object`|Объявление элемента объекта типа XAML, которое поддерживается общим типом CLR. Если `object` относится к типу XAML, который не из `object` пространства имен XAML по умолчанию, требуется префикс для обозначения пространства имен XAML, где `object` существует.|
|`typeString`|Строка, которая объявляет одно или несколько имен типа XAML строками, которая поставляет аргументы типа для общего типа CLR. Смотрите замечания для дополнительных примечаний синтаксиса.|

## <a name="remarks"></a>Примечания

В большинстве случаев типы XAML, которые `typeString` используются в качестве элемента информации в строке, являются префикатами. Типичные типы общих ограничений <xref:System.Int32> <xref:System.String>CLR (например, и) поступают из библиотек базового класса CLR. Эти библиотеки не отображаются в типичных пространствах имен XAML по умолчанию, и поэтому требуют отображения приставки для использования XAML.

Вы можете указать несколько имен типа XAML с помощью делимитеда запятой.

Если общие ограничения сами используют общие типы, аргументы типа вложенных ограничений могут содержаться скобками ().

Обратите внимание, `x:TypeArguments` что это определение специфична для .NET XAML Услуги и с использованием поддержки CLR. Определение уровня языка можно найти в [ \[разделе\] MS-XAML 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="usage-examples"></a>Примеры использования

В этих примерах предположим, что заявлены следующие определения пространства имен XAML:

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>Список\<струнных>

`<scg:List x:TypeArguments="sys:String" ...>`мгновенно новый <xref:System.Collections.Generic.List%601> с типом <xref:System.String> аргумента.

### <a name="dictionarystringstring"></a>Словарная\<строка, струнная>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`мгновенно новый <xref:System.Collections.Generic.Dictionary%602> с двумя <xref:System.String> аргументами типа.

### <a name="queuekeyvaluepairstringstring"></a>Очередь<строки KeyValuePair,\<струнная>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`мгновенно <xref:System.Collections.Generic.Queue%601> новый, который имеет ограничение <xref:System.Collections.Generic.KeyValuePair%602> с внутренним испорчить <xref:System.String> <xref:System.String>аргументы типа ограничения и .

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 и WPF Общие XAML Использования

Для использования XAML 2006 и XAML, который используется для приложений WPF, существуют следующие ограничения для `x:TypeArguments` общих типов и общих типов xAML в целом:

- Только корневой элемент файла XAML может поддерживать общее использование XAML, которое ссылается на общий тип.

- Корневой элемент должен отображаться на общем типе, по крайней мере, с аргументом одного типа. Например, <xref:System.Windows.Navigation.PageFunction%601>. Функции страницы являются основным сценарием для поддержки общего использования XAML в WPF.

- Элемент объекта корневого элемента XAML для общего `x:Class`элемента должен также объявить частичный класс с использованием. Это верно даже при определении действия по сборке WPF.

- `x:TypeArguments`не может ссылаться на вложенные общие ограничения.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 или XAML 2006 без Зависимости WPF 3.0 или WPF 3.5

В .NET XAML Services для XAML 2006 или XAML 2009, связанные с WPF ограничения на использование общего XAML смягчаются. Вы можете мгновенно настроить элемент общего объекта в любом положении в разметке XAML, которую может поддерживать система резервного типа и модель объекта.

Если вы используете XAML 2009 вместо отображения типов базовых CLR для получения типов XAML для примитивов общего `typeString`языка, вы можете использовать [встроенные типы для общих примитивов языка XAML](types-for-primitives.md) в качестве элементов информации в . Например, можно объявить следующее (фотофиксация не показана, но x является x-языком XAML namespace для XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

В WPF и при таргетинге .NET Framework 4 или .NET Core 3.0 (или `x:TypeArguments` позже) вы можете использовать функции XAML 2009 вместе с, но только для свободного XAML (XAML, который не разметка-компилируется). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009. Если вам нужно разметки компилировать XAML, вы должны работать в соответствии с ограничениями, отмеченные в разделе [XAML 2006 и WPF Generic XAML Usages.](#xaml-2006-and-wpf-generic-xaml-usages) BAML поддерживается только в рамках .NET.

## <a name="see-also"></a>См. также

- [Директива x:Class](xclass-directive.md)
- [Расширение разметки x:Type](xtype-markup-extension.md)
- [Встроенные типы для общих примитивов языка XAML](types-for-primitives.md)
- [Универсальные шаблоны в XAML](generics.md)
