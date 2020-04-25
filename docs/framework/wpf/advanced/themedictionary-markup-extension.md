---
title: Расширение разметки ThemeDictionary
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: 450956de1c7498bf2b92096b38ad2f64745a0b2d
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141099"
---
# <a name="themedictionary-markup-extension"></a>Расширение разметки ThemeDictionary
Предоставляет для разработчиков пользовательских элементов управления или приложений, которые объединяют элементы управления сторонних производителей, способ загрузки определенных темой словарей ресурсов для использования в стилизации элемента управления.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" ... />  
```  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`assemblyUri`|Универсальный код ресурса (URI) сборки, содержащей сведения о теме. Как правило, это URI типа pack, который ссылается на сборку в большом пакете. Ресурсы сборки и URI типа pack упрощают развертывание. Дополнительные сведения см. в разделе [URI типа pack в WPF](../app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Remarks  
 Это расширение предназначено для заполнения только одного конкретного значения свойства: значение для <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.  
  
 С помощью этого расширения можно указать только одну сборку с ресурсами, которая содержит некоторые стили, которые будут использоваться только при применении темы Windows Aero к системе пользователя, другие стили только в том случае, если тема Luna активна и т. д. Используя это расширение, содержимое словаря ресурсов элемента управления при необходимости можно автоматически считать недействительным и перезагрузить для другой темы.  
  
 `assemblyUri` Строка (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> значение свойства) образует основание соглашения об именовании, которое определяет, какой словарь применяется к конкретной теме. <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> Логика для `ThemeDictionary` завершает соглашение путем создания универсального кода ресурса (URI), указывающего на конкретный вариант словаря темы, который содержится в предварительно скомпилированной сборке ресурсов. Описание этого соглашения или взаимодействия темы со стилизацией основных элементов управления и стилизацией уровня страницы или приложения, как концепции, полностью в данном разделе не рассматривается. Базовый сценарий для использования `ThemeDictionary` заключается в указании <xref:System.Windows.ResourceDictionary.Source%2A> свойства объекта, `ResourceDictionary` объявленного на уровне приложения. При предоставлении универсального кода ресурса (URI) для `ThemeDictionary` сборки с помощью расширения, а не прямого URI, логика расширения предоставит логику недействительности, которая применяется при каждом изменении темы системы.  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `ThemeDictionary`, присваивается в качестве значения <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> соответствующего класса расширения <xref:System.Windows.ThemeDictionaryExtension>.  
  
 `ThemeDictionary` также можно использовать в синтаксисе элемента объекта. В этом случае указание значения <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> свойства обязательно.  
  
 Излишним может оказаться и использование `ThemeDictionary` в атрибуте, в котором свойство <xref:System.Windows.Markup.StaticExtension.Member%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" ... />  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `ThemeDictionary` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] В реализации процессора обработка этого расширения разметки определяется <xref:System.Windows.ThemeDictionaryExtension> классом.  
  
 `ThemeDictionary` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также

- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Ресурсы, Содержимое и Файлы данных WPF-приложения](../app-development/wpf-application-resource-content-and-data-files.md)
