---
title: Универсальные шаблоны в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432962"
---
# <a name="generics-in-xaml"></a>Универсальные шаблоны в XAML

.NET XAML Services, <xref:System.Xaml?displayProperty=fullName> реализованный в рамках поддержки использования общих типов CLR. Эта поддержка включает в себя указание ограничений генериков в качестве `Add` аргумента типа и обеспечение соблюдения ограничений путем вызова соответствующего метода для общих случаев сбора. Эта тема описывает аспекты использования и ссылки на генерические типы в XAML.

## <a name="xtypearguments"></a>x:ТипАргументы

`x:TypeArguments`является директивой, определяемой языком XAML. Когда он используется в качестве члена типа XAML, который `x:TypeArguments` поддерживается общим типом, передает ограничивающие аргументы типа общего для резервного конструктора. Для ссылки синтаксис, который относится к `x:TypeArguments`.NET XAML Услуги использования , который включает в себя примеры синтаксиса, см. [x:TypeArguments Directive](xtypearguments-directive.md)

Поскольку `x:TypeArguments` строка занимает строку и имеет резерваторную поддержку, она обычно объявляется в использовании XAML в качестве атрибута.

В потоке узлов XAML информация, `x:TypeArguments` заявленная, <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> может `StartObject` быть получена из позиции в потоке узлов. Значение возврата <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> — это <xref:System.Xaml.XamlType> список значений. Определение того, представляет ли тип XAML общий <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>тип, может быть сделано путем вызова.

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Правила и конвенции синтаксиса для генериков в XAML

В XAML общий тип всегда должен быть представлен в качестве ограниченного общего. Неограниченный универсал никогда не присутствует в системе типа XAML или потоке узлов XAML и не может быть представлен в разметке XAML. Общий может быть отображено в синтаксисе атрибута XAML для случаев, когда это вложенное ограничение типа общего, на который `x:TypeArguments`ссылается, или в тех случаях, когда `x:Type` поставляет ссылку типа CLR для общего типа. Общие ссылки поддерживаются через <xref:System.Xaml.Schema.XamlTypeTypeConverter> класс, определенный .NET XAML Services.

Форма синтаксиса атрибута <xref:System.Xaml.Schema.XamlTypeTypeConverter> XAML, включенная изменяет типичную конвенцию синтаксиса MSIL / CLR, которая использует угловые скобки для типов и ограничений генериков, а вместо этого заменяет скобки для контейнера с ограничением. Например, [см.](xtypearguments-directive.md)

## <a name="generics-and-xaml-2009-features"></a>Дженерики и XAML 2009 Особенности

Если вы используете XAML 2009 вместо отображения типов базовых CLR для получения типов XAML для примитивов `x:TypeArguments`общего языка, вы можете использовать [встроенные типы XAML 2009 в](types-for-primitives.md) качестве информационных элементов в . Например, можно объявить следующее (фотофиксация не `x` показана, но это пространство имен XAML language XAML для XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>Поддержка генериков в WPF

Для использования XAML 2006 при конкретной ориентации WPF, [x:Class](xclass-directive.md) также должен быть предоставлен на том же элементе, что `x:TypeArguments`и , и этот элемент должен быть корневым элементом в документе XAML. Корневой элемент должен отображаться на общем типе, по крайней мере, с аргументом одного типа. Например, <xref:System.Windows.Navigation.PageFunction%601>.

Возможные обходные пути для поддержки общих обычаев включают определение пользовательского расширения разметки, которое может вернуть общие типы, или предоставление определения класса упаковки, которое вытекает из общего типа, но выравнивает общее ограничение в своем собственном определении класса.

В WPF вы можете использовать функции XAML 2009 вместе с, `x:TypeArguments`но только для свободного XAML (XAML, который не разметка-компилируется). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.

Пользовательские рабочие процессы в Фонде рабочего процесса Windows для .NET Framework 3.5 не поддерживают общее использование XAML.

## <a name="see-also"></a>См. также

- [Директива x:TypeArguments](xtypearguments-directive.md)
- [Директива x:Class](xclass-directive.md)
- [Встроенные типы для общих примитивов языка XAML](types-for-primitives.md)
