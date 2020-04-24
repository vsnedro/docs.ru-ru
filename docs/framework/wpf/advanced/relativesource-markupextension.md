---
title: Расширение разметки RelativeSource
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 6301299da966ade9b5cc7ccd105c8269a486744e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646231"
---
# <a name="relativesource-markupextension"></a>Расширение разметки RelativeSource

Определяет свойства связывающего <xref:System.Windows.Data.RelativeSource> источника, который будет использоваться в [рамках расширения связывания разметки,](binding-markup-extension.md)или при настройке <xref:System.Windows.Data.Binding.RelativeSource%2A> свойства <xref:System.Windows.Data.Binding> элемента, установленного в XAML.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a>Использование атрибута XAML (вложенный в расширение Binding)

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

-или-

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`modeEnumValue`|Это может быть:<br /><br /> - Токен `Self`строки; соответствует как <xref:System.Windows.Data.RelativeSource> созданный с <xref:System.Windows.Data.RelativeSource.Mode%2A> его <xref:System.Windows.Data.RelativeSourceMode.Self>свойством установлен на .<br />- Токен `TemplatedParent`строки; соответствует как <xref:System.Windows.Data.RelativeSource> созданный с <xref:System.Windows.Data.RelativeSource.Mode%2A> его <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>свойством установлен на .<br />- Токен `PreviousData`строки; соответствует как <xref:System.Windows.Data.RelativeSource> созданный с <xref:System.Windows.Data.RelativeSource.Mode%2A> его <xref:System.Windows.Data.RelativeSourceMode.PreviousData>свойством установлен на .<br />- Смотрите ниже `FindAncestor` для получения информации о режиме.|
|`FindAncestor`|Строковая лексема `FindAncestor`. Использовании этой лексемы осуществляет переход в режим, где `RelativeSource` задает тип предка и (при необходимости) уровень предка. Это соответствует <xref:System.Windows.Data.RelativeSource> при создании со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого задано значение <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.|
|`typeName`|Требуется для режима `FindAncestor`. Имя типа, которое заполняет свойство <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|
|`intLevel`|Необязательно для режима `FindAncestor`. Уровень предка (вычисляется в направлении родителя в логическом дереве).|

## <a name="remarks"></a>Примечания

`{RelativeSource TemplatedParent}`обязательные обычаи являются ключевым методом, который учитывает более широкую концепцию разделения uI элемента управления и логику элемента управления. Это делает возможным привязку из определения шаблона к созданному по шаблону родительскому элементу (экземпляр объекта времени выполнения, в котором применяется шаблон). В этом случае [расширение шаблонной разметки](templatebinding-markup-extension.md) на самом деле `{Binding RelativeSource={RelativeSource TemplatedParent}}`является сокращением для следующего связывающего выражения: . `TemplateBinding`или `{RelativeSource TemplatedParent}` обычаи имеют отношение только в XAML, который определяет шаблон. Для получения дополнительной [TemplateBinding Markup Extension](templatebinding-markup-extension.md)информации см.

`{RelativeSource FindAncestor}`в основном используется в шаблонах управления или предсказуемых автономных композициях uI, в тех случаях, когда контроль всегда должен находиться в визуальном древе определенного типа предка. Например, элементы в элементе управления элементами могут использовать вхождения `FindAncestor` для привязки к свойствам предка элемента управления элементами. Либо элементы, которые являются частью композиции элемента управления в шаблоне, могут использовать привязки `FindAncestor` к родительским элементам в той же структуре композиции.

В синтаксисе объектного элемента для режима `FindAncestor`, показанного выше в разделах синтаксиса XAML, второй синтаксис объектного элемента используется специально для режима `FindAncestor`. Режим `FindAncestor` требует значения <xref:System.Windows.Data.RelativeSource.AncestorType%2A>. Необходимо установить <xref:System.Windows.Data.RelativeSource.AncestorType%2A> в качестве атрибута ссылку на расширение [x:Type Markup](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) к типу предка для поиска. Значение <xref:System.Windows.Data.RelativeSource.AncestorType%2A> используется при обработке запроса привязки во время выполнения.

Для режима `FindAncestor` необязательное свойство <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> может помочь устранить неоднозначность поиска предка в случаях, где в дереве элементов, возможно, существует более одного предка данного типа.

Дополнительные сведения об использовании режима `FindAncestor` см. в разделе <xref:System.Windows.Data.RelativeSource>.

`{RelativeSource Self}`полезен для сценариев, где одно свойство экземпляра должно зависеть от значения другого свойства того же экземпляра, и между этими двумя свойствами уже не существует общих отношений собственности зависимости (например, принуждения). Хотя на объекте редко существуют два свойства, такие, что значения буквально идентичны (и одинаково `Converter` набраны), `{RelativeSource Self}`можно также применить параметр к связке, которая имеет, и использовать преобразователь для преобразования между исходными и целевыми типами. Другой сценарий для `{RelativeSource Self}` является <xref:System.Windows.MultiDataTrigger>частью .

Например, следующий код XAML определяет такой элемент <xref:System.Windows.Shapes.Rectangle>, что независимо от того, какое значение вводится для свойства <xref:System.Windows.FrameworkElement.Width%2A>, объектом <xref:System.Windows.Shapes.Rectangle> всегда является квадрат: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

`{RelativeSource PreviousData}`полезен либо в шаблонах данных, либо в тех случаях, когда привязки используют сбор в качестве источника данных. Можно выделить `{RelativeSource PreviousData}` взаимосвязь между смежными элементами данных в коллекции. Соответствующей методикой является установление привязки <xref:System.Windows.Data.MultiBinding> между текущим и предыдущим элементами в источнике данных и использование преобразователя в этой привязке для определения различия между двумя элементами и их свойствами.

В следующем примере первый элемент <xref:System.Windows.Controls.TextBlock> в шаблоне элементов отображает текущий номер. Второй <xref:System.Windows.Controls.TextBlock> привязкой <xref:System.Windows.Data.MultiBinding> является то, <xref:System.Windows.Data.Binding> что номинально имеет два компонента: текущая запись, и `{RelativeSource PreviousData}`связывание, которое намеренно использует предыдущую запись данных с помощью . Затем преобразователь в объекте <xref:System.Windows.Data.MultiBinding> вычисляет разницу и возвращает ее в привязку.

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
```

Описание связывания данных как концепции здесь не рассматривается, [см.](../../../desktop-wpf/data/data-binding-overview.md)

В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации процессора XAML обработка этого расширения <xref:System.Windows.Data.RelativeSource> разметки определяется классом.

`RelativeSource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в `{` XAML используют и `}` символы в их синтаксисе атрибута, который является конвенцией, с помощью которой процессор XAML признает, что расширение разметки должно обрабатывать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Data.Binding>
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения об объявлении привязок](../data/binding-declarations-overview.md)
- [Расширение разметки x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
