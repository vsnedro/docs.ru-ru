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
ms.openlocfilehash: f6ba0fe45aa11063c79d673b26794072968f4200
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646192"
---
# <a name="themedictionary-markup-extension"></a>Расширение разметки ThemeDictionary
Предоставляет для разработчиков пользовательских элементов управления или приложений, которые объединяют элементы управления сторонних производителей, способ загрузки определенных темой словарей ресурсов для использования в стилизации элемента управления.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
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
|`assemblyUri`|Единый идентификатор ресурсов (URI) сборки, содержащий информацию о теме. Как правило, это URI типа pack, который ссылается на сборку в большом пакете. Ресурсы сборки и URI типа pack упрощают развертывание. Дополнительные сведения см. в разделе [URI типа pack в WPF](../app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Примечания  
 Это расширение предназначено для заполнения только одного <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>конкретного значения свойства: значение для .  
  
 С помощью этого расширения можно указать одну сборку только для ресурсов, которая содержит некоторые стили для использования только тогда, когда тема Windows Aero применяется к системе пользователя, другим стилям только тогда, когда тема Luna активна, и так далее. Используя это расширение, содержимое словаря ресурсов элемента управления при необходимости можно автоматически считать недействительным и перезагрузить для другой темы.  
  
 Строка `assemblyUri` <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> (значение свойства) составляет основу конвенции именования, которая определяет, какой словарь применяется для конкретной темы. Логика <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> `ThemeDictionary` завершения конвенции путем создания единого идентификатора ресурсов (URI), который указывает на определенный вариант словаря темы, который содержится в предварительно компилированной сборке ресурсов. Описание этого соглашения или взаимодействия темы со стилизацией основных элементов управления и стилизацией уровня страницы или приложения, как концепции, полностью в данном разделе не рассматривается. Базовый сценарий `ThemeDictionary` использования заключается в определении <xref:System.Windows.ResourceDictionary.Source%2A> свойства `ResourceDictionary` заявленного на уровне приложения. При предоставлении URI для сборки через `ThemeDictionary` расширение, а не в качестве прямого URI, логика расширения будет предоставлять логику недействительности, которая применяется всякий раз, когда тема системы изменяется.  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `ThemeDictionary`, присваивается в качестве значения <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> соответствующего класса расширения <xref:System.Windows.ThemeDictionaryExtension>.  
  
 `ThemeDictionary` также можно использовать в синтаксисе элемента объекта. В этом случае требуется указание <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> стоимости имущества.  
  
 Излишним может оказаться и использование `ThemeDictionary` в атрибуте, в котором свойство <xref:System.Windows.Markup.StaticExtension.Member%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `ThemeDictionary` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации процессора обработка этого расширения разметки определяется классом. <xref:System.Windows.ThemeDictionaryExtension>  
  
 `ThemeDictionary` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также раздел

- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Ресурсы, Содержимое и Файлы данных WPF-приложения](../app-development/wpf-application-resource-content-and-data-files.md)
