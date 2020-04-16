---
title: расширение разметки x:Reference
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432656"
---
# <a name="xreference-markup-extension"></a>расширение разметки x:Reference

Ссылки на экземпляр, объявленный в другом месте в разметке XAML. Ссылка относится к `x:Name`элементу .

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`instancexName`|Значение `x:Name` (или значение <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>идентифицированного свойства) указанного экземпляра.|

## <a name="remarks"></a>Примечания

`x:Reference`обеспечивает поддержку на уровне языков XAML для концепции ссылки на элементы, которая в противном случае была реализована в конкретных рамках, таких как WPF.

## <a name="xreference-and-wpf"></a>x:Справка и WPF

В WPF и XAML 2006 ссылки на элементы <xref:System.Windows.Data.Binding.ElementName%2A> рассматриваются с помощью функции связывания на уровне рамочной системы. Для большинства приложений и <xref:System.Windows.Data.Binding.ElementName%2A> сценариев WPF по-прежнему следует использовать привязку. Исключенияизмвателями в это общее руководство могут быть случаи, когда существует контекст данных или другие соображения, которые делают нецелесообразными связывание данных и когда компиляция разметки не участвует.

`x:Reference`— конструкция, определяемая в XAML 2009. В WPF можно использовать возможности XAML 2009, но только для кода XAML, не скомпилированного с разметкой WPF. Скомпилированный XAML с разметкой и форма BAML кода XAML пока не поддерживают ключевые слова языка и компоненты XAML 2009.
