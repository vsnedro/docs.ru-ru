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
ms.openlocfilehash: 4cdba2a61be4e9686cd2120fd90a213534c222c8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243366"
---
# <a name="componentresourcekey-markup-extension"></a>Расширение разметки ComponentResourceKey
Определяет и ссылается на ключи для ресурсов, загруженных из внешних сборок. Это позволяет поиску ресурсов указать целевой тип в сборке, а не словарь явного ресурса в сборке или в классе.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Использование атрибутов XAML (установка ключа, компактный)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Использование атрибутов XAML (установка ключа, многословная)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Использование атрибутов XAML (запросный ресурс, компактный)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Использование атрибутов XAML (запросресурс, многословный)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`targetTypeName`|Имя типа общего языка (CLR), определяемого в сборке ресурсов.|  
|`targetID`|Ключ для ресурса. Когда ресурсы будут `targetID` рассмотрены, будет аналогична [директиве x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) ресурса.|  
  
## <a name="remarks"></a>Remarks  
 Как видно из приведенных выше`ComponentResourceKey`обычаев, использование расширения разметки находится в двух местах:  
  
- Определение ключа в словаре тематиного ресурса, как это предусмотрено автором элемента управления.  
  
- Доступ к ресурсу темы из сборки, когда вы retemplating управления, но хотите использовать значения свойств, которые приходят из ресурсов, предоставляемых темами элемента управления.  
  
 Для ссылок на компонентные ресурсы, которые приходят из `{DynamicResource}` тем, `{StaticResource}`как правило, рекомендуется использовать, а не . Это показано в использовании. `{DynamicResource}`рекомендуется, потому что сама тема может быть изменена пользователем. Если требуется ресурс компонента, который наиболее точно соответствует намерениям автора элемента управления для поддержки темы, следует включить ссылку на ресурс компонента также динамической.  
  
 Идентифицирует <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> тип, существующий в целевой сборке, где фактически определен ресурс. A `ComponentResourceKey` может быть определен и использован независимо <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> от точного знания, где определяется, но в конечном итоге должны решить тип через ссылки сборок.  
  
 Общее использование <xref:System.Windows.ComponentResourceKey> для определения ключей, которые затем подвергаются как члены класса. Для этого использования используется <xref:System.Windows.ComponentResourceKey> конструктор класса, а не расширение разметки. Для получения дополнительной <xref:System.Windows.ComponentResourceKey>информации см. [Control Authoring Overview](../controls/control-authoring-overview.md)  
  
 Для создания ключей и ссылок на ресурсы с ключами `ComponentResourceKey` для расширения разметки обычно используется синтаксис атрибутов.  
  
 Показано, что компактный синтаксис зависит от подписи <xref:System.Windows.ComponentResourceKey.%23ctor%2A> конструктора и использования позиционного параметра расширения разметки. Порядок, `targetTypeName` в `targetID` котором и даны важно. Многословный синтаксис опирается <xref:System.Windows.ComponentResourceKey.%23ctor%2A> на безпаративный <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> конструктор, а затем устанавливает и <xref:System.Windows.ComponentResourceKey.ResourceId%2A> таким образом, что аналогично истинному синтаксису атрибута на элементе объекта. В многословном синтаксисе порядок, в котором установлены свойства, не имеет значения. Взаимоотношения и механизмы этих двух альтернатив (компактный и многословный) описаны более подробно в теме [Markup Extensions и WPF XAML](markup-extensions-and-wpf-xaml.md).  
  
 Технически значение для `targetID` любого объекта, он не должен быть строкой. Тем не менее, наиболее распространенным `targetID` использованием в WPF является выравнивание значения с формами, которые являются строками, и где такие строки действительны в [XamlName Грамматика](../../../desktop-wpf/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey`может быть использован в синтаксисе элемента объекта. В этом случае для правильной <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> инициализации расширения требуется указание значения как свойств, так и <xref:System.Windows.ComponentResourceKey.ResourceId%2A> свойств.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации чтения обработка этого расширения разметки определяется классом. <xref:System.Windows.ComponentResourceKey>  
  
 `ComponentResourceKey` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
