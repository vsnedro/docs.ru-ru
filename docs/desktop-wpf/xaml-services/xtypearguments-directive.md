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
ms.openlocfilehash: 430ab65af52282ccb1d429cd2523efe213f13609
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543555"
---
# <a name="xtypearguments-directive"></a>Директива x:TypeArguments

Передает ограничивающие аргументы типа универсального класса в конструктор универсального типа.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`object`|Объявление объектного элемента типа XAML, который поддерживается универсальным типом CLR. Если `object` ссылается на тип XAML, который не относится к пространству имен XAML по умолчанию, `object` требуется префикс, указывающий пространство имен XAML, где `object` существует.|
|`typeString`|Строка, объявляющая одно или несколько имен типов XAML в виде строк, которые предоставляют аргументы типа для универсального типа CLR. Дополнительные сведения о синтаксисе см. в разделе Примечания.|

## <a name="remarks"></a>Примечания

В большинстве случаев типы XAML, используемые в качестве информационного элемента в `typeString` строке, являются префиксами. Типичные типы универсальных ограничений CLR (например, <xref:System.Int32> и <xref:System.String> ) поступают из библиотек базовых классов среды CLR. Эти библиотеки не сопоставляются с типичными пространствами имен XAML по умолчанию для конкретной платформы, поэтому для использования XAML требуется сопоставление префикса.

Можно указать несколько имен типов XAML, используя разделитель-запятую.

Если универсальные ограничения сами по себе используют универсальные типы, аргументы типа вложенного ограничения могут содержаться в круглых скобках ().

Обратите внимание, что это определение `x:TypeArguments` характерно для служб XAML .NET и использует резервное копирование среды CLR. Определение уровня языка можно найти в [ \[ \] разделе 5.3.11 в MS-XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="usage-examples"></a>Примеры использования

В этих примерах предполагается, что объявляются следующие определения пространства имен XAML:

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>Числ\<String>

`<scg:List x:TypeArguments="sys:String" ...>` создает новый объект <xref:System.Collections.Generic.List%601> с <xref:System.String> аргументом типа.

### <a name="dictionarystringstring"></a>Dictionary\<String,String>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` создает новый экземпляр <xref:System.Collections.Generic.Dictionary%602> с двумя <xref:System.String> аргументами типа.

### <a name="queuekeyvaluepairstringstring"></a>Очередь<KeyValuePair\<String,String>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` создает новый объект <xref:System.Collections.Generic.Queue%601> , имеющий ограничение <xref:System.Collections.Generic.KeyValuePair%602> с аргументами типа внутреннего ограничения <xref:System.String> и <xref:System.String> .

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>Общие сведения об использовании XAML в XAML 2006 и WPF

Для использования XAML 2006 и XAML, используемого для приложений WPF, в целом существуют следующие ограничения на `x:TypeArguments` Использование универсального типа из XAML.

- Только корневой элемент файла XAML может поддерживать универсальное использование XAML, которое ссылается на универсальный тип.

- Корневой элемент должен сопоставляться с универсальным типом по крайней мере с одним аргументом типа. Например, <xref:System.Windows.Navigation.PageFunction%601>. Страничные функции являются основным сценарием для поддержки общего использования XAML в WPF.

- Элемент объекта XAML корневого элемента для универсального класса должен также объявлять разделяемый класс с помощью `x:Class` . Это справедливо даже при определении действия построения WPF.

- `x:TypeArguments` невозможно сослаться на вложенные универсальные ограничения.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 или XAML 2006 без зависимостей WPF 3,0 или WPF 3,5

В службах .NET XAML для XAML 2006 или XAML 2009 ограничения, связанные с WPF, для универсального использования XAML нестрогие. Можно создать экземпляр универсального элемента объекта в любой позиции в разметке XAML, которую может поддерживать система резервных типов и модель объектов.

При использовании XAML 2009 вместо сопоставления базовых типов CLR для получения типов XAML для общих языковых примитивов можно использовать [встроенные типы для общих примитивов языка XAML](types-for-primitives.md) в качестве информационных элементов в `typeString` . Например, можно объявить следующее (сопоставление префиксов не показано, но x является пространством имен XAML языка XAML для XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

В WPF и при нацеливании на .NET Framework 4 или .NET Core 3,0 (или более поздней версии) можно использовать функции XAML 2009 вместе с, `x:TypeArguments` но только для свободного XAML (XAML, не скомпилированный разметкой). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009. Если необходимо скомпилировать XAML в разметку, необходимо использовать ограничения, указанные в разделе [об использовании xaml 2006 и WPF Generic XAML](#xaml-2006-and-wpf-generic-xaml-usages) . BAML поддерживается только в .NET Framework.

## <a name="see-also"></a>См. также

- [Директива x:Class](xclass-directive.md)
- [Расширение разметки x:Type](xtype-markup-extension.md)
- [Встроенные типы для общих примитивов языка XAML](types-for-primitives.md)
- [Универсальные шаблоны в XAML](generics.md)
