---
title: Директива x:Name
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: 9f812a49a3217a563be1bd7f1d999b641c28463d
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432716"
---
# <a name="xname-directive"></a>Директива x:Name

Уникально идентифицирует XAML-определенные элементы в названии XAML. XAML namescopes и их модели уникальности могут быть применены к мгновенным объектам, когда фреймворки предоставляют AI или реализуют поведение, которое получает доступ к графику объектов, созданному XAML во время выполнения.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`XAMLNameValue`|Строка, которая соответствует ограничениям [XamlName Грамматика](xamlname-grammar.md).|

## <a name="remarks"></a>Примечания

После `x:Name` того, как оно применяется к модели резервного программирования платформы, имя эквивалентно переменной, в основе которого содержится ссылка на объект, или экземпляр, возвращенный конструктором.

Значение использования `x:Name` директивы должно быть уникальным в namescope XAML. По умолчанию при использовании .NET XAML Services API основной гименскоп XAML определяется в корневом элементе XAML одного производства XAML и включает элементы, содержащиеся в этом производстве XAML. Дополнительные дискретные именные скопы XAML, которые могут возникнуть в рамках одного производства XAML, могут быть определены рамками для решения конкретных сценариев. Например, в WPF новые именные скопы XAML определяются и создаются любым шаблоном, который также определяется на этом производстве XAML. Для получения дополнительной информации о XAML namescopes (написано для WPF, но актуально для многих концепций XAML namescope), [см.](../../framework/wpf/advanced/wpf-xaml-namescopes.md)

В общем, `x:Name` не должны применяться `x:Key`в ситуациях, которые также используют . Внедрение XAML с помощью конкретных существующих `x:Key` `x:Name`рамок ввело концепции замещения между и, но это не рекомендуется. .NET XAML Services не поддерживает такие концепции замены <xref:System.Windows.Markup.INameScope> при <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>обработке информации об имени/ключах, такой как или .

Правила выдачи `x:Name` разрешений, а также применение уникальности названия потенциально определяются конкретными инфраструктурами реализации. Однако, чтобы использовать сяочку с помощью услуг .NET XAML, рамочные определения <xref:System.Windows.Markup.INameScope> уникальности XAML namescope должны соответствовать определению информации в этой документации и должны использовать те же правила относительно того, где применяется информация. Например, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] реализация делит различные элементы <xref:System.Windows.NameScope> разметки на отдельные диапазоны, такие как словари ресурсов, логическое дерево, созданное XAML уровня страницы, шаблоны и другое отложенное содержание, а затем обеспечивает уникальность имени XAML в каждом из этих имен XAML.

Для пользовательских типов, которые используют "SAML Services XAML" (saML, можно настроить или изменить свойство, к которое можно отойти `x:Name` на тип. Это поведение определяется ссылками на имя свойства для <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> отображения с кодом определения типа.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>является атрибутом уровня типа.

Using.NET XAML Services, логика поддержки XAML namescope может быть определена <xref:System.Windows.Markup.INameScope> в нейтральном для фрейм-нейтрального порядке путем реализации интерфейса.

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

В стандартной конфигурации [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] сборки для приложения, использующем XAML, `x:Name` частичных классов и за кодом, указанное [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] становится именем поля, созданного в базовом коде при обработке задачей компиляции разметки, и это поле содержит ссылку на объект. По умолчанию созданное поле является внутренним. Вы можете изменить доступ к полю, указав [атрибут x:FieldModifier.](xfieldmodifier-directive.md) В WPF и Silverlight последовательность состоит в том, что компиляция разметки определяет и называет поле в частичном классе, но значение изначально пусто. Затем сгенерированный `InitializeComponent` метод, названный, вызывается изнутри конструктора класса. `InitializeComponent`состоит `FindName` из вызовов, `x:Name` использующих каждое из значений, которые существуют в xAML-определенной части частичного класса в качестве строк ввода. Значения возврата затем присваиваются ссылке на поле с похожим названием для заполнения значений поля объектами, созданными в результате разбора XAML. Выполнение `InitializeComponent` позволяет ссылаться на график объекта времени `x:Name` выполнения, используя прямое название `FindName` поля, вместо того, чтобы звонить прямо в любое время, когда вам нужна ссылка на объект, определяемый XAML.

Для приложения WPF, использующего целевые показатели Microsoft `Page` Visual Basic и включающий файлы XAML с действием сборки, во время компиляции создается отдельное эталонное свойство, которое добавляет `WithEvents` ключевое слово ко всем `x:Name`элементам, которые имеют, для поддержки `Handles` синтаксиса для делегатов обработчика событий. Это свойство всегда является общедоступным. Дополнительные сведения см. в разделе [Обработка событий в Visual Basic и WPF](../../framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).

`x:Name`используется процессором WPF XAML для регистрации имени в XAML namescope во время загрузки, даже в тех случаях, когда страница не разметка компилируется по действиям сборки (например, свободный XAML словаря ресурсов). Одна из причин такого `x:Name` поведения заключается <xref:System.Windows.Data.Binding.ElementName%2A> в том, что это потенциально необходимо для связывания. Для получения подробной информации [см.](../data/data-binding-overview.md)

Как упоминалось `x:Name` ранее, (или `Name`) не должны `x:Key`применяться в ситуациях, которые также используют . Имеет [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> особое поведение определения себя как XAML namescope, но возвращение <xref:System.Windows.Markup.INameScope> не реализованных или нулевых значений для AIS как способ обеспечения этого поведения. Если parser WPF XAML `Name` `x:Name` сталкивается или в <xref:System.Windows.ResourceDictionary>XAML-определенных , имя не добавляется к любому XAML namescope. Попытка найти это имя из любого XAML namescope и `FindName` методы не вернет действительные результаты.

### <a name="xname-and-name"></a>x:Имя и имя

Многие сценарии приложений WPF `x:Name` могут избежать `Name` использования атрибута, поскольку свойство зависимости, указанное в пространстве <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> имен XAML по умолчанию для нескольких важных базовых классов, таких как и удовлетворяет этой же цели. По-прежнему существует несколько распространенных сценариев XAML `Name` и WPF, в которых важен доступ к коду к элементу без свойств на уровне фреймворка. Например, некоторые классы поддержки анимации `Name` и раскадровки не поддерживают свойство, но они часто нуждаются в коде для управления анимацией. Вы должны `x:Name` указать в качестве атрибута на временные линии и преобразования, которые создаются в XAML, если вы собираетесь ссылаться на них из кода позже.

Если <xref:System.Windows.FrameworkElement.Name%2A> он доступен в качестве <xref:System.Windows.FrameworkElement.Name%2A> `x:Name` свойства в классе и может быть использован как атрибуты, но исключение для разбора приведет, если оба указаны на одном элементе. Если xAML составлена разметка, исключение будет происходить на компиляции разметки, в противном случае это происходит на нагрузке.

<xref:System.Windows.FrameworkElement.Name%2A>может быть установлен с помощью синтаксиса <xref:System.Windows.DependencyObject.SetValue%2A>атрибута XAML, а также в коде с использованием; Обратите внимание, <xref:System.Windows.FrameworkElement.Name%2A> однако, что установка свойства в коде не создает репрезентативную ссылку на поле в xAML namescope в большинстве случаев, когда XAML уже загружен. Вместо того, чтобы <xref:System.Windows.FrameworkElement.Name%2A> пытаться <xref:System.Windows.NameScope> установить код, используйте методы из кода, против соответствующего namescope.

<xref:System.Windows.FrameworkElement.Name%2A>также может быть установлен с помощью синтаксиса элемента свойства с внутренним текстом, но это редкость. В отличие `x:Name` от этого, не может быть установлен в <xref:System.Windows.DependencyObject.SetValue%2A>синтаксисе элемента свойства XAML, или в коде с использованием; его можно установить только с помощью синтаксиса атрибутов на объектах, поскольку он является директивой.

## <a name="silverlight-usage-notes"></a>Примечания к использованию Silverlight

`x:Name`для Silverlight документируется отдельно. Для получения дополнительной информации [см. Языковые особенности (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>См. также

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Деревья в WPF](../../framework/wpf/advanced/trees-in-wpf.md)
