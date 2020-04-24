---
title: Расширение разметки DynamicResource
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: 5ccda8ba8f41a30e0ce1c832a6d3176b7fb8e8c2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646259"
---
# <a name="dynamicresource-markup-extension"></a>Расширение разметки DynamicResource
Обеспечивает значение для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] любого атрибута свойства, отложив это значение как ссылку на определенный ресурс. Поведение поиска этого ресурса аналогично поиску времени выполнения.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Использование элемента свойства XAML  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`key`|Ключ для запрашиваемого ресурса. Этот ключ был первоначально назначен [директивой x:Key,](../../../desktop-wpf/xaml-services/xkey-directive.md) если ресурс был создан `key` в разметке, или был предоставлен в качестве параметра при вызове, <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> если ресурс был создан в коде.|  
  
## <a name="remarks"></a>Примечания  
 A `DynamicResource` создаст временное выражение во время первоначальной компиляции и, таким образом, отсрояет поиск ресурсов до тех пор, пока не потребуется запрашиваемая стоимость ресурса для построения объекта. Это потенциально может быть [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] после загрузки страницы. Значение ресурса будет найдено на основе поиска ключей против всех словарей активных ресурсов, начиная с текущей области страницы, и заменяется выражением заполнителя из компиляции.  
  
> [!IMPORTANT]
> С точки зрения приоритета свойства `DynamicResource` зависимости выражение эквивалентно позиции, в которой применяется динамическая ссылка на ресурс. Если вы установите локальное значение для `DynamicResource` свойства, которое `DynamicResource` ранее имело выражение в качестве локального значения, то значение полностью удаляется. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](dependency-property-value-precedence.md).  
  
 Некоторые сценарии доступа к `DynamicResource` ресурсам особенно подходят для в отличие от [расширения StaticResource Markup.](staticresource-markup-extension.md) См [XAML Ресурсы](../../../desktop-wpf/fundamentals/xaml-resources-define.md) для обсуждения относительных `DynamicResource` достоинств `StaticResource`и последствий производительности и .  
  
 Указанный <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> должен соответствовать существующему ресурсу, определяемому [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) на определенном уровне на странице, приложении, доступных темах управления и внешних ресурсах или системных ресурсах, и поиск ресурсов будет происходить в этом порядке. Для получения дополнительной информации о поиске ресурсов для статических и динамических ресурсов [см.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)  
  
 Ключом ресурса может быть любая строка, определяемая в [грамматике XamlName.](../../../desktop-wpf/xaml-services/xamlname-grammar.md) Ключом ресурса также могут быть другие типы объектов, такие как <xref:System.Type>. Ключ <xref:System.Type> имеет основополагающее значение для того, как элементы управления могут быть стилизованы по темам. Дополнительные сведения см. в разделе [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md).  
  
 AUP для поиска значений ресурсов, <xref:System.Windows.FrameworkElement.FindResource%2A>таких как, следуют той же `DynamicResource`логике поиска ресурсов, что и в.  
  
 Альтернативным декларативным средством ссылки на ресурс является [расширение StaticResource Markup.](staticresource-markup-extension.md)  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `DynamicResource`, присваивается в качестве значения <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> соответствующего класса расширения <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource`может быть использован в синтаксисе элемента объекта. В этом случае требуется указание <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> стоимости имущества.  
  
 Излишним может оказаться и использование `DynamicResource` в атрибуте, в котором свойство <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `DynamicResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации процессора обработка этого расширения разметки определяется классом. <xref:System.Windows.DynamicResourceExtension>  
  
 `DynamicResource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также раздел

- [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Ресурсы и код](resources-and-code.md)
- [Директива x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Расширение разметки StaticResource](staticresource-markup-extension.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
