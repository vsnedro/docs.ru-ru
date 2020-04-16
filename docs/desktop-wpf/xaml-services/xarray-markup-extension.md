---
title: Расширение разметки x:Array
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433286"
---
# <a name="xarray-markup-extension"></a>Расширение разметки x:Array

Обеспечивает общую поддержку массивов объектов в XAML через расширение разметки. Это соответствует типу `x:ArrayExtension` XAML в «MS-XAML».

## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`typeName`|Имя типа, который `x:Array` будет содержать ваш. `typeName`может быть (и часто) префиксируется для пространства имен XAML, содержащего определения типа XAML.|
|`arrayContents`|Содержимое элементов, присвоенное свойству. `ArrayExtension.Items` Как правило, эти элементы определяются как `x:Array` один или несколько элементов объекта, содержащиеся в тегах открытия и закрытия. Объекты, указанные здесь, как ожидается, будут `typeName`присваиваться типу XAML, указанному в .|

## <a name="remarks"></a>Примечания

`Type`является необходимым атрибутом `x:Array` для всех элементов объекта. Значение `Type` параметра не требуется `x:Type` для использования расширения разметки; коротким названием типа является тип XAML, который может быть указан как строка.

В реализации .NET XAML Services взаимосвязь между входним типом XAML и выходным CLR <xref:System.Type> созданного массива зависит от контекста службы для расширения разметки. Выход <xref:System.Type> — <xref:System.Xaml.XamlType.UnderlyingType%2A> это тип ввода XAML, после <xref:System.Xaml.XamlType> поиска необходимого контекста схемы <xref:System.Windows.Markup.IXamlTypeResolver> XAML и службы, предоставляемой контекстом.

При обработке содержимое массива `ArrayExtension.Items` присваивается свойству. В <xref:System.Windows.Markup.ArrayExtension> реализации это представлено <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.

В реализации .NET XAML Services обработка этого расширения <xref:System.Windows.Markup.ArrayExtension> разметки определяется классом. <xref:System.Windows.Markup.ArrayExtension>не запечатан и может быть использован в качестве основы для реализации расширения разметки для пользовательского типа массива.

`x:Array`больше предназначендля для общей расширяемости языка в XAML. Но `x:Array` также может быть полезно для указания значений XAML определенных свойств, которые принимают XAML-поддерживаемые коллекции в качестве структурированного содержимого свойства. Например, можно указать содержимое <xref:System.Collections.IEnumerable> свойства `x:Array` с использованием.

`x:Array` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. `x:Array`частично является исключением из этого правила, поскольку `x:Array` вместо альтернативной обработки значений атрибутов предусмотрена альтернативная обработка содержимого внутреннего текста. Такое поведение позволяет группам типов, которые не могут быть поддержаны существующей моделью содержимого, быть сгруппированы в массив и упомянутые позднее в коде позади, приодя к названному массиву; вы можете <xref:System.Array> вызвать методы, чтобы получить отдельные элементы массива.

Все расширения разметки в XAML{,} `)` используют скобки (в их синтаксисе атрибута, который является конвенцией, по которой процессор XAML признает, что расширение разметки должно обрабатывать значение атрибута. Для получения дополнительной информации о расширениях разметки в целом [см.](type-converters-and-markup-extensions.md)

В XAML 2009, `x:Array` определяется как язык примитивный вместо расширения разметки. Для получения дополнительной [Built-in Types for Common XAML Language Primitives](types-for-primitives.md)информации см.

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

Как правило, `x:Array` элементы объекта, которые населяют, не являются элементами, которые существуют в пространстве имен [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML, и требуют отображения приставки к непо умолчанию XAML namespace.

Например, ниже приводится простой массив из `sys` двух строк, `x`с приставкой (а также) определенным на уровне массива.

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

Для пользовательских типов, которые используются в качестве элементов массива, класс должен также поддерживать требования к мгновенному использованию в XAML в качестве элементов объекта. Для получения дополнительной [XAML and Custom Classes for WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)информации см.

## <a name="see-also"></a>См. также

- [Расширения разметки и XAML WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Типы, перенесенные из WPF в System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
