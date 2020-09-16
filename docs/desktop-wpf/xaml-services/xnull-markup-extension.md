---
title: Расширение разметки x:NULL
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: f4971d61d11ec14eaeac2d2f202353e4921b9325
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549448"
---
# <a name="xnull-markup-extension"></a>Расширение разметки x:NULL

Задает `null` в качестве значения для элемента XAML.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>Примечания

Ключевое слово для пустой ссылки в C# и C++ равно null. Ключевое слово Microsoft Visual Basic для пустой ссылки — это `Nothing` , но всегда используется `{x:Null}` как использование XAML, независимо от того, какой язык кода программной части связан с XAML.

`x:Null`Расширение разметки не имеет устанавливаемых свойств.

Использование значения NULL часто связано с выдержкой из XAML-элемента в <xref:System.Nullable%601> значении CLR.

`x:Null`Расширение разметки, как и все расширения разметки XAML, использует фигурные скобки ( `{,}` ) для экранирования обработки значений атрибутов, отличных от литералов или ссылок обработчиков событий. Синтаксис атрибутов — это синтаксис, который чаще всего используется с этим расширением разметки. Синтаксис объектного элемента `<x:Null />` технически возможен, но редко используется, так как `x:Null` расширение разметки не имеет параметров позиционирования или аргументов конструкции.

Дополнительные сведения о расширениях разметки см. в разделе [расширения разметки и XAML WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).

В службах .NET XAML обработка этого расширения разметки определяется <xref:System.Windows.Markup.NullExtension> классом.

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

Обратите внимание, что `null` не обязательно является начальным значением свойства зависимости ссылочного типа. Начальное значение по умолчанию может различаться для каждого свойства зависимости и может быть основано на метаданных, относящихся к свойству. Многие свойства зависимостей не принимаются `null` в качестве значения с помощью разметки или кода из-за реализаций обратного вызова проверки. См. сведения о [свойствах зависимостей](/dotnet/desktop/wpf/advanced/dependency-properties-overview).

## <a name="see-also"></a>См. также

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Обзор XAML (WPF)](../fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
