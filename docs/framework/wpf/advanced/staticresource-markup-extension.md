---
title: Расширение разметки StaticResource
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 5c0bb247bae525658d89d53f1672e57b87aba7bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646209"
---
# <a name="staticresource-markup-extension"></a>Расширение разметки StaticResource
Обеспечивает значение для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] любого атрибута свойства, ища ссылку на уже определенный ресурс. Поведение поиска этого ресурса аналогично поиску времени загрузки, который будет искать ресурсы, которые ранее [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] были загружены из разметки текущей страницы, а также других источников приложения, и будет генерировать эту ценность ресурса в качестве значения свойства в объектах времени выполнения.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`key`|Ключ для запрашиваемого ресурса. Этот ключ был первоначально назначен [директивой x:Key,](../../../desktop-wpf/xaml-services/xkey-directive.md) если ресурс был создан `key` в разметке, или был предоставлен в качестве параметра при вызове, <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> если ресурс был создан в коде.|  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
> Не `StaticResource` должен пытаться сделать передний ссылку на ресурс, который определяется лексически дальше в файле. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Попытка сделать это не поддерживается, и даже если такая ссылка не подведет неудачу, попытка передовая ссылка <xref:System.Windows.ResourceDictionary> понесет штраф за время загрузки при поиске внутренних таблиц хэша, представляющих a. Для достижения наилучших результатов отрегулируйте состав словарей ресурсов таким образом, чтобы можно было избежать переадресов. Если вы не можете избежать переадресов, используйте [расширение динамической разметки.](dynamicresource-markup-extension.md)  
  
 Указанный <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> должен соответствовать существующему ресурсу, идентифицированному с [директивой x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) на определенном уровне на вашей странице, приложении, доступных темах управления и внешних ресурсах или системными ресурсами. Поиск ресурсов происходит в этом порядке. Для получения дополнительной информации о поведении поиска ресурсов для статических и динамических ресурсов [см.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)  
  
 Ключ омича может быть любой строкой, определенной в [грамматике XamlName.](../../../desktop-wpf/xaml-services/xamlname-grammar.md) Ключом ресурса также могут быть другие типы объектов, такие как <xref:System.Type>. Ключ <xref:System.Type> имеет основополагающее значение для того, как элементы управления могут быть стилизованы по темам, через неявный ключ стиля. Дополнительные сведения см. в разделе [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md).  
  
 Альтернативным декларативным средством ссылки на ресурс является [расширение динамической разметки.](dynamicresource-markup-extension.md)  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `StaticResource`, присваивается в качестве значения <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> соответствующего класса расширения <xref:System.Windows.StaticResourceExtension>.  
  
 `StaticResource`может быть использован в синтаксисе элемента объекта. В этом случае требуется указание <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> стоимости имущества.  
  
 Излишним может оказаться и использование `StaticResource` в атрибуте, в котором свойство <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `StaticResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации процессора обработка этого расширения разметки определяется классом. <xref:System.Windows.StaticResourceExtension>  
  
 `StaticResource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также раздел

- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Ресурсы и код](resources-and-code.md)
