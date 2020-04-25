---
title: Расширение разметки ComponentResourceKey
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: f86b7000b97bbc1287347947a9244c24a7de74c2
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141128"
---
# <a name="componentresourcekey-markup-extension"></a>Расширение разметки ComponentResourceKey
Определяет и ссылается на ключи для ресурсов, загружаемых из внешних сборок. Это позволяет подстановке ресурсов указывать целевой тип в сборке, а не явный словарь ресурсов в сборке или классе.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Использование атрибута XAML (ключ Setting, компактный)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Использование атрибута XAML (параметр key, verbose)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Использование атрибута XAML (запрос ресурса, компактный)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Использование атрибута XAML (запрос ресурса, подробный)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" ... />  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`targetTypeName`|Имя общедоступного типа общеязыковой среды выполнения (CLR), определенного в сборке ресурсов.|  
|`targetID`|Ключ для ресурса. При поиске ресурсов `targetID` они будут аналогом [директивы x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) ресурса.|  
  
## <a name="remarks"></a>Remarks  
 Как показано в описании выше, использование расширения разметки {`ComponentResourceKey`} находится в двух местах:  
  
- Определение ключа в словаре ресурсов темы, предоставленное автором элемента управления.  
  
- Доступ к ресурсу темы из сборки при пересоздании шаблона элемента управления, но необходимо использовать значения свойств, полученные из ресурсов, предоставляемых темами элемента управления.  
  
 Для ссылок на ресурсы компонентов, которые поступают из тем, обычно рекомендуется использовать `{DynamicResource}` вместо. `{StaticResource}` Это показано в использовании. `{DynamicResource}`рекомендуется, поскольку пользователь может изменить саму тему. Если требуется, чтобы ресурс компонента, наиболее точно соответствующий намерению разработчика элемента управления, поддерживал тему, следует включить также динамическую ссылку на ресурс компонента.  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> Определяет тип, существующий в целевой сборке, в которой ресурс фактически определен. `ComponentResourceKey` Можно определить и использовать независимо от того, где <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> определено, но в конечном итоге необходимо разрешить тип с помощью сборок, на которые имеются ссылки.  
  
 Распространенный способ использования <xref:System.Windows.ComponentResourceKey> — определение ключей, которые затем предоставляются как члены класса. Для такого использования используется конструктор <xref:System.Windows.ComponentResourceKey> класса, а не расширение разметки. Дополнительные сведения см <xref:System.Windows.ComponentResourceKey>. в разделе или «определение и создание ссылок на ключи для ресурсов темы» раздела [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)раздела.  
  
 Для установки ключей и ссылок на ресурсы с ключом синтаксис атрибутов обычно используется для расширения `ComponentResourceKey` разметки.  
  
 Синтаксис Compact, показанный в, зависит <xref:System.Windows.ComponentResourceKey.%23ctor%2A> от сигнатуры конструктора и использования позиционированного параметра для расширения разметки. Порядок, в котором задаются `targetTypeName` и `targetID` , важен. Подробный синтаксис основывается на конструкторе <xref:System.Windows.ComponentResourceKey.%23ctor%2A> без параметров, а затем устанавливает <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> и <xref:System.Windows.ComponentResourceKey.ResourceId%2A> таким образом, что аналогично истинному синтаксису атрибута для объектного элемента. В подробном синтаксисе порядок, в котором задаются свойства, не важен. Отношения и механизмы этих двух вариантов (компактный и подробный) более подробно описаны в разделе [расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 Технически значением параметра `targetID` может быть любой объект, а не строковый. Однако наиболее распространенным применением в WPF является согласование `targetID` значения с формами, которые являются строками, и если такие строки допустимы в [грамматике имяxaml](../../../desktop-wpf/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey`может использоваться в синтаксисе объектного элемента. В этом случае для правильной инициализации расширения требуется указать значения <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> свойств <xref:System.Windows.ComponentResourceKey.ResourceId%2A> и.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] В реализации модуля чтения Обработка этого расширения разметки определяется <xref:System.Windows.ComponentResourceKey> классом.  
  
 `ComponentResourceKey` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
