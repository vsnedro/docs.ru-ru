---
title: Общие сведения об объявлении привязок
description: Узнайте, как объявить привязку в XAML для разработки приложений в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
ms.openlocfilehash: 8d4943de0cacb5fe0b5a0c37a5a68f15243ad528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619641"
---
# <a name="binding-declarations-overview"></a>Общие сведения об объявлении привязок

В этом разделе описываются различные способы объявления привязок.

<a name="Prereq"></a>

## <a name="prerequisites"></a>Предварительные требования

Важно, чтобы перед прочтением этого раздела вы были знакомы с основными понятиями и принципами использования расширений разметки. Подробнее о расширениях разметки см. в разделе [Расширения разметки и XAML WPF](../advanced/markup-extensions-and-wpf-xaml.md).

В этом разделе не рассматриваются сведения о привязке данных. Описание концепции привязки данных см. в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).

<a name="BindinginXAML"></a>

## <a name="declaring-a-binding-in-xaml"></a>Объявление привязки в XAML

В этом разделе описывается объявление привязки в XAML.

<a name="MarkupExtensionSyntax"></a>

### <a name="markup-extension-usage"></a>Использование расширения разметки

<xref:System.Windows.Data.Binding> является расширением разметки. Если для объявления привязки вы используете расширение привязки, то объявление состоит из ряда предложений, следующих за ключевым словом `Binding` и разделенных запятыми (,). Предложения в объявлении привязки могут следовать в любом порядке, и существует множество различных комбинаций. Предложения представляют собой пары *имя* = -*значение* , где *Name* — это имя <xref:System.Windows.Data.Binding> свойства, а *value* — значение, которое устанавливается для свойства.

При создании строк объявления привязки в разметке они должны быть присоединены к конкретному свойству зависимостей целевого объекта. В следующем примере показано, как привязать <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> свойство с помощью расширения привязки, указав <xref:System.Windows.Data.Binding.Source%2A> Свойства и <xref:System.Windows.Data.Binding.Path%2A> .

[!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#L37-L37)]

Таким образом можно указать большую часть свойств <xref:System.Windows.Data.Binding> класса. Дополнительные сведения о расширении привязки, а также список <xref:System.Windows.Data.Binding> свойств, которые не могут быть заданы с помощью расширения привязки, см. в разделе Общие сведения о [расширении разметки привязки](../advanced/binding-markup-extension.md) .

<a name="ObjectElementSyntax"></a>

### <a name="object-element-syntax"></a>Синтаксис объектных элементов

Синтаксис объектных элементов является альтернативой созданию объявления привязки. В большинстве случаев нет каких-то специальных преимуществ в использовании либо только расширения разметки, либо только синтаксиса объектных элементов. Но в тех случаях, когда расширение разметки не подходит конкретно для вашего сценария (например, если значение свойства имеет нестроковый тип, для которого не существует преобразования), то следует использовать синтаксис объектных элементов.

Ниже приведен пример использования синтаксиса объектных элементов и расширения разметки:

[!code-xaml[BindConversionMarkup#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]

В этом примере свойство привязывается <xref:System.Windows.Controls.TextBlock.Foreground%2A> путем объявления привязки с помощью синтаксиса расширения. В объявлении привязки для <xref:System.Windows.Controls.TextBlock.Text%2A> свойства используется синтаксис объектного элемента.

Дополнительные сведения о различных терминах см. в разделе [Подробное описание синтаксиса XAML](../advanced/xaml-syntax-in-detail.md).

<a name="MBandPB"></a>

### <a name="multibinding-and-prioritybinding"></a>Классы MultiBinding и PriorityBinding

<xref:System.Windows.Data.MultiBinding>и <xref:System.Windows.Data.PriorityBinding> не поддерживают синтаксис расширения XAML. Поэтому при объявлении <xref:System.Windows.Data.MultiBinding> или в XAML необходимо использовать синтаксис объектного элемента <xref:System.Windows.Data.PriorityBinding> .

<a name="BindinginCode"></a>

## <a name="creating-a-binding-in-code"></a>Создание привязки в коде

Другой способ указания привязки заключается в задании свойств непосредственно для <xref:System.Windows.Data.Binding> объекта в коде. В следующем примере показано, как создать <xref:System.Windows.Data.Binding> объект и указать свойства в коде.  В этом примере `TheConverter` — это объект, реализующий <xref:System.Windows.Data.IValueConverter> интерфейс.

[!code-csharp[BindConversion#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
[!code-vb[BindConversion#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]

Если привязка объекта является <xref:System.Windows.FrameworkElement> или, <xref:System.Windows.FrameworkContentElement> можно вызвать `SetBinding` метод непосредственно для объекта вместо использования <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> . Пример см. в разделе [Создание привязки в коде](how-to-create-a-binding-in-code.md).

<a name="Path_Syntax"></a>

## <a name="binding-path-syntax"></a>Синтаксис пути привязки

Используйте <xref:System.Windows.Data.Binding.Path%2A> свойство, чтобы указать исходное значение, к которому необходимо выполнить привязку:

- В самом простом случае <xref:System.Windows.Data.Binding.Path%2A> значением свойства является имя свойства исходного объекта, используемого для привязки, например `Path=PropertyName` .

- Вложенные свойства свойства могут быть заданы с помощью аналогичного синтаксиса, как в C#. Например, предложение `Path=ShoppingCart.Order` задает привязку к подсвойству `Order` объекта или свойства `ShoppingCart`.

- Для привязки присоединенного свойства заключите его в скобки. Например, для привязки к присоединенному свойству <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> используется синтаксис `Path=(DockPanel.Dock)` .

- Индексаторы свойства можно указать в квадратных скобках после имени свойства, для которого применяется индексатор. Например, предложение `Path=ShoppingCart[0]` задает привязку к индексу, который соответствует способу, который внутренняя индексация свойства использует для обработки символьной строки "0". Также поддерживаются вложенные индексаторы.

- Индексаторы и вложенные свойства могут сочетаться в предложении `Path`, например, `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`

- Индексаторы могут иметь несколько внутренних параметров, разделенных запятыми (,). Тип каждого параметра указывается в скобках. Например, вы можете задать предложение `Path="[(sys:Int32)42,(sys:Int32)24]"`, где `sys` сопоставляется с пространством имен `System`.

- Если источником является представлением коллекции, текущий элемент можно указать с косой чертой (/). Например, предложение `Path=/` задает привязку к текущему элементу в представлении. Если источником является коллекция, этот синтаксис задает текущий элемент представления коллекции по умолчанию.

- Имена свойств и косые черты можно объединять для обхода свойств, которые являются коллекциями. Например, предложение `Path=/Offices/ManagerName` задает текущий элемент коллекции источников, где свойство `Offices` также является коллекцией. Текущий элемент этой коллекции — объект, содержащий свойство `ManagerName`.

- При необходимости для привязки к текущему источнику можно использовать путь в виде точки (.). Например, предложение `Text="{Binding}"` эквивалентно предложению `Text="{Binding Path=.}"`.

### <a name="escaping-mechanism"></a>Механизм экранирования

- Внутри индексаторов ([]) знак крышки (^) задает экранирование следующего символа.

- Если вы задали <xref:System.Windows.Data.Binding.Path%2A> в XAML, вам также потребуется экранировать (с помощью сущностей XML) определенные символы, которые являются специальными для определения языка XML:

  - Используйте `&amp;` для экранирования символа "&".

  - Используйте `&gt;` для экранирования закрывающего тега ">".

- Кроме того, если вы задаете всю привязку в атрибуте, используя синтаксис расширения разметки, необходимо экранировать (с помощью обратной косой черты \\) символы, которые являются специфическими для синтаксического анализатора расширения разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

  - Обратная косая черта (\\) сама по себе является escape-символом.

  - Знак равенства (=) разделяет имя свойства и значение этого свойства.

  - Запятая (,) отделяет свойства друг от друга.

  - Закрывающая фигурная скобка (}) указывает конец расширения разметки.

<a name="Default"></a>

## <a name="default-behaviors"></a>Поведение по умолчанию

Поведение по умолчанию выглядит следующим образом, если не указано в объявлении.

- Создается преобразователь по умолчанию, который пытается выполнить преобразование типов между значением источника привязки и значением целевого объекта привязки. Если преобразование не удается выполнить, преобразователь по умолчанию возвращает значение `null`.

- Если значение не задано <xref:System.Windows.Data.Binding.ConverterCulture%2A> , подсистема привязки использует `Language` свойство целевого объекта привязки. В языке XAML это свойство по умолчанию имеет значение "en-US" или наследует свое значение от корневого элемента (или любого элемента) страницы, если оно было задано явным образом.

- При условии, что привязка уже имеет контекст данных (например, контекст данных, наследуемый от родительского элемента), а объект или коллекция, возвращаемые этим контекстом, подходят для привязки без необходимости дополнительного изменения пути, объявление привязки может вообще не иметь предложений: `{Binding}`. Таким способом привязка часто задается для стилей данных, где привязка воздействует на коллекцию. Дополнительные сведения см. в подразделе "Использование всего объекта в качестве источника привязки" раздела [Общие сведения об источниках привязки](binding-sources-overview.md).

- Значение по умолчанию <xref:System.Windows.Data.Binding.Mode%2A> варьируется между односторонним и двусторонним в зависимости от привязанного свойства зависимостей. Режим привязки всегда можно объявить явным образом, чтобы обеспечить требуемое поведение привязки. В общем случае изменяемые пользователем свойства элемента управления, такие как <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> и <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType> , по умолчанию имеют двусторонние привязки, тогда как большинство других свойств по умолчанию являются односторонними привязками.

- Значение по умолчанию <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> различается в <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> зависимости от <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> привязанного свойства зависимостей. Значение по умолчанию для большинства свойств зависимостей — <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, а свойство <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> имеет значение по умолчанию <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.

## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Практические руководства](data-binding-how-to-topics.md)
- [Привязка данных](../advanced/optimizing-performance-data-binding.md)
- [Синтаксис PropertyPath XAML](../advanced/propertypath-xaml-syntax.md)
