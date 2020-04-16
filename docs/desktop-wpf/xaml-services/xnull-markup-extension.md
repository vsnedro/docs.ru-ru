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
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432698"
---
# <a name="xnull-markup-extension"></a>Расширение разметки x:NULL

`null` Определяется как значение для участника XAML.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>Примечания

Ключевое слово для нулевой ссылки в СЗ и СЗ является нулевым. Ключевое слово Microsoft Visual Basic `Nothing`для нулевой `{x:Null}` ссылки, но вы всегда используете в качестве использования XAML независимо от того, какой код за языком вы связываете с XAML.

Расширение `x:Null` разметки не имеет установленных свойств.

Использование нулевой часто связано с экспозицией члена <xref:System.Nullable%601> XAML значения CLR.

Расширение `x:Null` разметки, как и все расширения разметки`{,}`XAML, использует скобки () для избежания обработки значений атрибутов, чтобы быть иным, чем буквальные или события обработчик ссылки. Синтаксис атрибутов является синтаксисом, наиболее часто используемым с этим расширением разметки. Синтаксис `<x:Null />` элемента объекта технически возможен, но `x:Null` редко используется, поскольку расширение разметки не имеет позиционных параметров или аргументов конструкции.

Для получения информации о расширениях разметки см. [Расширение разметки и WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

В службах .NET XAML обработка этого расширения <xref:System.Windows.Markup.NullExtension> разметки определяется классом.

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

Обратите `null` внимание, что это не обязательно начальное неустановленное значение для свойства зависимости эталонного типа. Начальное значение по умолчанию может варьироваться для каждого свойства зависимости и может быть основано на метаданных, специфичных свойствах. Многие свойства зависимости `null` не принимаются в качестве значения, либо через разметку, либо код из-за их реализации возврата проверки. Для получения дополнительной информации [Dependency Properties Overview](../../framework/wpf/advanced/dependency-properties-overview.md)о свойствах зависимостей см.

## <a name="see-also"></a>См. также

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Обзор XAML (WPF)](../fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
