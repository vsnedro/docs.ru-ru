---
title: Общие сведения о шаблонах данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: b9e55eac1c72cd3deec21754373da4364a7cfed2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646463"
---
# <a name="data-templating-overview"></a>Общие сведения о шаблонах данных
Модель шаблонов данных WPF предоставляет большую гибкость при определении представления данных. Элементы управления WPF имеют встроенные функции для поддержки настройки представления данных. Эта тема сначала демонстрирует, <xref:System.Windows.DataTemplate> как определить, а затем вводит другие функции шаблонов данных, такие как выбор шаблонов на основе пользовательской логики и поддержка отображения иерархических данных.

<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования
 В этом разделе рассматриваются функции шаблонов данных. Здесь отсутствуют общие сведения о понятиях привязки данных. Сведения о базовых концепциях привязки данных содержатся в разделе [Обзор привязки данных](../../../desktop-wpf/data/data-binding-overview.md).

 <xref:System.Windows.DataTemplate>о представлении данных и является одной из многих особенностей, предоставляемых WPF укладка и шаблонная модель. Для введения модели укладки и шаблонирования WPF, например, <xref:System.Windows.Style> как использовать набор свойств [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md) на элементах управления, см.

 Кроме того, важно понимать, `Resources`какие объекты, по <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> сути, позволяют объекты, такие как и быть многоразовыми. Дополнительные сведения о ресурсах см. в разделе [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

<a name="DataTemplating_Basic"></a>
## <a name="data-templating-basics"></a>Основные сведения о шаблонах данных

 Чтобы продемонстрировать, почему <xref:System.Windows.DataTemplate> это важно, давайте рассмотрим пример связывания данных. В этом примере <xref:System.Windows.Controls.ListBox> у нас есть список объектов. `Task` Каждому `Task` объекту соответствует `TaskName` (строка), `Description` (строка), `Priority` (int) и свойство типа `TaskType`, которое является `Enum` со значениями `Home` и `Work`.

 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]

<a name="without_a_datatemplate"></a>
### <a name="without-a-datatemplate"></a>Без шаблона данных DataTemplate
 Без <xref:System.Windows.DataTemplate>, <xref:System.Windows.Controls.ListBox> наши в настоящее время выглядит следующим образом:

 ![Шаблонные данные образец скриншот](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")

 Происходит то, что без каких-либо <xref:System.Windows.Controls.ListBox> конкретных `ToString` инструкций, по умолчанию звонки при попытке отобразить объекты в коллекции. Таким образом, `Task` если объект `ToString` переопределяет <xref:System.Windows.Controls.ListBox> метод, то отображается представление строки каждого исходного объекта в базовой коллекции.

 Например, если класс `Task` переопределяет метод `ToString` таким образом, что `name` — поле для `TaskName` свойства:

 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]

 Тогда <xref:System.Windows.Controls.ListBox> выглядит следующим образом:

 ![Шаблонные данные образец скриншот](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")

 Тем не менее это характеризуется ограниченностью и негибкостью. Кроме того, если вы привязываетесь к данным XML, вы не сможете переопределить. `ToString`

<a name="defining_simple_datatemplate"></a>
### <a name="defining-a-simple-datatemplate"></a>Определение простого шаблона DataTemplate
 Решение заключается в <xref:System.Windows.DataTemplate>определении . Один из способов сделать <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> это, <xref:System.Windows.Controls.ListBox> чтобы <xref:System.Windows.DataTemplate>установить свойство к . То, что <xref:System.Windows.DataTemplate> вы указываете в вашем становится визуальной структурой объекта данных. Ниже <xref:System.Windows.DataTemplate> можно довольно просто. Мы даем инструкции, что каждый элемент появляется в виде трех <xref:System.Windows.Controls.TextBlock> элементов в пределах <xref:System.Windows.Controls.StackPanel>. Каждый <xref:System.Windows.Controls.TextBlock> элемент привязан к `Task` свойству класса.

 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]

 Базовыми данными для примеров этой темы является коллекция объектов CLR. Если вы привязываетесь к данным XML, фундаментальные понятия одинаковы, но есть небольшое синтаксическую разницу. Например, вместо `Path=TaskName`того, чтобы <xref:System.Windows.Data.Binding.XPath%2A> `@TaskName` иметь, `TaskName` вы бы установить (если атрибут вашего узла XML).

 Теперь <xref:System.Windows.Controls.ListBox> наш внешний вид:

 ![Шаблонные данные образец скриншот](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")

<a name="defining_datatemplate_as_a_resource"></a>
### <a name="creating-the-datatemplate-as-a-resource"></a>Создание шаблона DataTemplate как ресурса
 В приведенном выше примере мы определили <xref:System.Windows.DataTemplate> вливую. Обычно его определяют в разделе ресурсов, чтобы его можно было повторно использовать, как в следующем примере:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Теперь вы можете использовать `myTaskTemplate` в качестве ресурса, как показано в следующем примере:

 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]

 Поскольку `myTaskTemplate` это ресурс, теперь его можно использовать на других <xref:System.Windows.DataTemplate> элементах управления, которые имеют свойство, которое занимает тип. Как показано выше, для <xref:System.Windows.Controls.ItemsControl> объектов, таких <xref:System.Windows.Controls.ListBox>как, это свойство. <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Для <xref:System.Windows.Controls.ContentControl> объектов это <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> свойство.

<a name="Styling_DataType"></a>
### <a name="the-datatype-property"></a>Свойство DataType
 Класс <xref:System.Windows.DataTemplate> имеет <xref:System.Windows.DataTemplate.DataType%2A> свойство, которое <xref:System.Windows.Style> <xref:System.Windows.Style.TargetType%2A> очень похоже на свойство класса. Таким образом, вместо `x:Key` указания <xref:System.Windows.DataTemplate> для приведенного выше примера, вы можете сделать следующее:

 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]

 Это <xref:System.Windows.DataTemplate> автоматически применяется `Task` ко всем объектам. Обратите внимание, что в этом случае `x:Key` устанавливается неявно. Поэтому, если вы <xref:System.Windows.DataTemplate> присвоите это `x:Key` значение, `x:Key` вы <xref:System.Windows.DataTemplate> переопределяете неявное и не будет применяться автоматически.

 Если вы привязываете <xref:System.Windows.Controls.ContentControl> `Task` к коллекции объектов, то <xref:System.Windows.Controls.ContentControl> они не используют вышеупомянутое <xref:System.Windows.DataTemplate> автоматически. Это происходит потому, <xref:System.Windows.Controls.ContentControl> что привязка к необходимой дополнительной информации, чтобы различать, хотите ли вы привязаться ко всей коллекции или отдельным объектам. Если <xref:System.Windows.Controls.ContentControl> вы отслеживаете выбор <xref:System.Windows.Controls.ItemsControl> типа, вы можете <xref:System.Windows.Data.Binding.Path%2A> установить <xref:System.Windows.Controls.ContentControl> свойство`/`привязки к «, чтобы указать, что вы заинтересованы в текущем элементе. Для примера см. [Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). В противном случае <xref:System.Windows.DataTemplate> необходимо указать <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> явное указание, установив свойство.

 Свойство <xref:System.Windows.DataTemplate.DataType%2A> особенно полезно, когда <xref:System.Windows.Data.CompositeCollection> у вас есть различные типы объектов данных. Пример см. в разделе [Реализация CompositeCollection](how-to-implement-a-compositecollection.md).

<a name="adding_more_to_datatemplate"></a>
## <a name="adding-more-to-the-datatemplate"></a>Добавление дополнительных данных в DataTemplate
 В настоящее время данные содержат необходимую информацию, но определенно это можно улучшить. Давайте усовершенствуем презентацию, <xref:System.Windows.Controls.Border>добавив <xref:System.Windows.Controls.Grid>a , <xref:System.Windows.Controls.TextBlock> и некоторые элементы, которые описывают данные, которые отображаются.

 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 Следующий скриншот показывает <xref:System.Windows.Controls.ListBox> с этим <xref:System.Windows.DataTemplate>измененным:

 ![Шаблонные данные образец скриншот](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")

 Мы можем <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.HorizontalAlignment.Stretch> установить <xref:System.Windows.Controls.ListBox> на, чтобы убедиться, что ширина элементов занимает все пространство:

 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]

 С <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> свойством, <xref:System.Windows.HorizontalAlignment.Stretch>установленным на, теперь <xref:System.Windows.Controls.ListBox> выглядит следующим образом:

 ![Шаблонные данные образец скриншот](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")

<a name="DataTrigger_to_Apply_Property_Values"></a>
### <a name="use-datatriggers-to-apply-property-values"></a>Использование триггеров данных для применения значений свойств
 В настоящей презентации не говорится о том, является ли `Task` домашней задачей или офисной. Помните, что объект `Task` имеет свойство `TaskType` типа `TaskType`, который является перечислением со значениями `Home` и `Work`.

 В следующем примере <xref:System.Windows.DataTrigger> <xref:System.Windows.Controls.Border.BorderBrush%2A> наборы элемента, указанного `border` `TaskType.Home` `Yellow` в том, является ли свойство `TaskType` .

 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 Наше приложение теперь выглядит следующим образом. Домашние задачи отображаются с желтой границей, а офисные — с синей границей:

 ![Шаблонные данные образец скриншот](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")

 В этом <xref:System.Windows.DataTrigger> примере <xref:System.Windows.Setter> используется значение свойства. Классы триггеров <xref:System.Windows.TriggerBase.EnterActions%2A> также <xref:System.Windows.TriggerBase.ExitActions%2A> имеют свойства и свойства, которые позволяют начать набор действий, таких как анимация. Кроме того, существует <xref:System.Windows.MultiDataTrigger> также класс, который позволяет применять изменения, основанные на нескольких значениях свойств, связанных с данными.

 Альтернативный способ достижения того же эффекта заключается в том, чтобы привязать <xref:System.Windows.Controls.Border.BorderBrush%2A> свойство к `TaskType` свойству и использовать преобразователь значений, чтобы вернуть цвет на основе `TaskType` значения. Создание вышеупомянутого эффекта с помощью преобразователя является немного более эффективным с точки зрения производительности. Кроме того, создание собственных преобразователей обеспечивает большую гибкость, так как вы предоставляете свою собственную логику. В конечном счете выбор техники зависит от сценария и предпочтений. Для получения информации о том, <xref:System.Windows.Data.IValueConverter>как написать конвертер, см.

<a name="what_belongs_in_datatemplate"></a>
### <a name="what-belongs-in-a-datatemplate"></a>Что входит в DataTemplate?

В предыдущем примере мы поместили <xref:System.Windows.DataTemplate> триггер <xref:System.Windows.DataTemplate.Triggers%2A?displayProperty=nameWithType> в свойство. Триггер <xref:System.Windows.Setter> устанавливает значение свойства элемента <xref:System.Windows.Controls.Border> (элемента), находящихся внутри <xref:System.Windows.DataTemplate>. Однако, если свойства, которые `Setters` вас беспокоят, не являются <xref:System.Windows.DataTemplate>свойствами элементов, которые находятся <xref:System.Windows.Style> в пределах <xref:System.Windows.Controls.ListBoxItem> текущего, это может быть <xref:System.Windows.Controls.ListBox>более подходящим для установки свойств, которые для класса (если элемент, который вы связывания является ). Например, если вы <xref:System.Windows.Trigger> хотите, чтобы <xref:System.Windows.UIElement.Opacity%2A> вы анифицировать значение элемента, когда мышь <xref:System.Windows.Controls.ListBoxItem> указывает на элемент, вы определяете триггеры в стиле. Пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

 В целом, имейте <xref:System.Windows.DataTemplate> в виду, что применяется к каждому из сгенерированных <xref:System.Windows.Controls.ListBoxItem> (для получения дополнительной информации о том, как и где он на самом деле применяется, см. <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Ваш <xref:System.Windows.DataTemplate> заботится только о представлении и внешнем виде объектов данных. В большинстве случаев все другие аспекты презентации, такие как то, как выглядит элемент при его выборе или как <xref:System.Windows.Controls.ListBox> излагаются элементы, не относятся к определению <xref:System.Windows.DataTemplate>. Пример см. в разделе [Стилизация и использование шаблонов для ItemsControl](#DataTemplating_ItemsControl).

<a name="Styling_StyleSelection"></a>
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Выбор DataTemplate на основе свойств объекта данных
 В разделе [Свойство DataType](#Styling_DataType) мы говорили о том, что можно определить различные шаблоны данных для различных объектов данных. Это особенно полезно, когда <xref:System.Windows.Data.CompositeCollection> у вас есть различные типы или коллекции с элементами различных типов. В разделе [«Использование DataTriggers to Apply Values»](#DataTrigger_to_Apply_Property_Values) мы показали, что если у вас есть <xref:System.Windows.DataTemplate> коллекция одного и того же типа объектов данных, вы можете создать триггеры, а затем использовать триггеры для применения изменений, основанных на значениях свойств каждого объекта данных. Тем не менее, хотя триггеры позволяют применить значения свойств или запустить анимацию, они не предоставляют гибкость, достаточную для реконструкции структуры объектов данных. Некоторые сценарии могут потребовать <xref:System.Windows.DataTemplate> создания различных для объектов данных, которые имеют один и тот же тип, но имеют различные свойства.

 Например, если объект `Task` имеет значение `Priority` свойства `1`, вы можете задать совершенно другой вид для него, чтобы сделать его сигналом оповещения. В этом случае создается <xref:System.Windows.DataTemplate> для отображения высокоприоритетных `Task` объектов. Давайте добавим следующее <xref:System.Windows.DataTemplate> в раздел ресурсов:

 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]

В этом примере используется свойство [DataTemplate.Resources.](xref:System.Windows.FrameworkTemplate.Resources%2A) Ресурсы, определяемые в <xref:System.Windows.DataTemplate>этом разделе, разделяются элементами в пределах .

 Чтобы предоставить логику, <xref:System.Windows.DataTemplate> нужно `Priority` выбрать, какой из них использовать <xref:System.Windows.Controls.DataTemplateSelector> на основе <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> значения объекта данных, создайте подкласс и переопределить метод. В следующем примере <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> метод предоставляет логику возврата соответствующего шаблона `Priority` на основе значения свойства. Шаблон для возврата находится в ресурсах обволакивающий <xref:System.Windows.Window> элемент.

 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]

 Затем можно объявить `TaskListDataTemplateSelector` как ресурс:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Чтобы использовать ресурс селектора шаблона, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> присвоите его свойству <xref:System.Windows.Controls.ListBox>. Вызывает <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> метод `TaskListDataTemplateSelector` для каждого из элементов в основной коллекции. Вызов передает объект данных в качестве параметра элемента. Возвращается <xref:System.Windows.DataTemplate> метод, который затем применяется к объекту данных.

 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]

 С селектора шаблона <xref:System.Windows.Controls.ListBox> на месте, теперь отображается следующим образом:

 ![Шаблонные данные образец скриншот](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")

Это заключительный шаг нашего обсуждения данного примера. Полный пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>
## <a name="styling-and-templating-an-itemscontrol"></a>Стилизация и использование шаблонов для ItemsControl
 Несмотря <xref:System.Windows.Controls.ItemsControl> на то, что это не <xref:System.Windows.DataTemplate> единственный тип управления, с которым <xref:System.Windows.Controls.ItemsControl> можно использовать, это очень распространенный сценарий, чтобы привязать к коллекции. В разделе Что принадлежит в разделе [DataTemplate,](#what_belongs_in_datatemplate) мы <xref:System.Windows.DataTemplate> обсудили, что определение вашего должно быть связано только с представлением данных. Для того, чтобы знать, когда <xref:System.Windows.DataTemplate> это не подходит для использования важно понимать <xref:System.Windows.Controls.ItemsControl>различные свойства стиля и шаблона, предоставляемые . Следующий пример предназначен для демонстрации функции каждого из этих свойств. В <xref:System.Windows.Controls.ItemsControl> этом примере связана `Tasks` с той же коллекцией, что и в предыдущем примере. Для демонстрационных целей все стили и шаблоны в этом примере объявлены встроенными.

 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]

 Ниже приведен снимок экрана примера при его просмотре:

 ![Снимок экрана: пример ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")

 Обратите внимание, что <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>вместо использования, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>вы можете использовать . Пример см. в предыдущем разделе. Аналогичным образом, вместо <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>использования, у вас <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>есть возможность использовать .

 Два других типа, связанных <xref:System.Windows.Controls.ItemsControl> свойства, которые <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>не показаны здесь и .

<a name="DataTemplating_HeirarchicalDataTemplate"></a>
## <a name="support-for-hierarchical-data"></a>Поддержка иерархических данных
 Пока мы только рассматривали как привязывать и отображать одну коллекцию. Иногда встречается коллекция, содержащая другие коллекции. Класс <xref:System.Windows.HierarchicalDataTemplate> предназначен для использования <xref:System.Windows.Controls.HeaderedItemsControl> с типами для отображения таких данных. В следующем примере `ListLeagueList` является списком объектов `League`. Каждый объект `League` содержит `Name` и коллекцию объектов `Division`. Каждый `Division` содержит `Name` и коллекцию объектов `Team`, и каждый объект `Team` содержит `Name`.

 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]

 Пример показывает, что с <xref:System.Windows.HierarchicalDataTemplate>помощью, вы можете легко отображать данные списка, который содержит другие списки. Ниже приведен снимок экрана примера.

 ![ИерархическиеDataTemplate образец скриншот](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")

## <a name="see-also"></a>См. также раздел

- [Связывание данных](../advanced/optimizing-performance-data-binding.md)
- [Поиск элементов, генерируемых DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о стилях заголовков столбцов GridView и шаблонах](../controls/gridview-column-header-styles-and-templates-overview.md)
