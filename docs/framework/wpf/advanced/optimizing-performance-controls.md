---
title: Оптимизация производительности элемента управления
description: Windows Presentation Foundation включает множество общих компонентов, используемых в большинстве приложений Windows. Узнайте, как повысить производительность пользовательского интерфейса.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
ms.openlocfilehash: de348dd93e5710b5b81af035ec7aa56e01dc4981
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168301"
---
# <a name="optimizing-performance-controls"></a>Оптимизация производительности: элементы управления

Windows Presentation Foundation (WPF) включает многие общие компоненты пользовательского интерфейса, используемые в большинстве приложений Windows. В этом разделе описываются методы повышения производительности пользовательского интерфейса.

## <a name="displaying-large-data-sets"></a>Отображение больших наборов данных

Элементы управления WPF, такие как <xref:System.Windows.Controls.ListView> и <xref:System.Windows.Controls.ComboBox> , используются для вывода списков элементов в приложении. Если отображаемый список большой, это может повлиять на производительность приложения. Причина этого в том, что стандартная система макета создает контейнер макета для каждого элемента, связанного с элементом управления «Список», и вычисляет размер и положение его макета. Как правило, не требуется отображать все элементы одновременно; можно отображать подмножество элементов, и пользователь будет прокручивать список. В этом случае имеет смысл использовать *виртуализацию* пользовательского интерфейса, что означает, что создание контейнера элемента и вычисление связанной разметки для элемента откладывается до тех пор, пока этот элемент не станет видимым.

Виртуализация пользовательского интерфейса является важным аспектом элементов управления «Список». Не следует путать виртуализацию пользовательского интерфейса с виртуализацией данных. Виртуализация пользовательского интерфейса хранит в памяти только видимые элементы, но в сценариях привязки данных хранит в памяти всю структуру данных. В отличие от этого виртуализация данных хранит в памяти только элементы данных, которые отображаются.

По умолчанию виртуализация пользовательского интерфейса включена для <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ListBox> элементов управления и, когда их элементы списка привязаны к данным. <xref:System.Windows.Controls.TreeView>виртуализацию можно включить, задав <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> для присоединенного свойства значение `true` . Если вы хотите включить виртуализацию пользовательского интерфейса для пользовательских элементов управления, которые являются производными от <xref:System.Windows.Controls.ItemsControl> или существующих элементов управления, использующих <xref:System.Windows.Controls.StackPanel> класс, например <xref:System.Windows.Controls.ComboBox> , можно установить значение и равным <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> <xref:System.Windows.Controls.VirtualizingStackPanel> <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> `true` . К сожалению, вы можете отключить виртуализацию пользовательского интерфейса для этих элементов управления, не осознавая этого. Ниже приведен список условий, отключающих виртуализацию пользовательского интерфейса.

- Контейнеры элементов добавляются непосредственно в <xref:System.Windows.Controls.ItemsControl> . Например, если приложение явно добавляет <xref:System.Windows.Controls.ListBoxItem> объекты в <xref:System.Windows.Controls.ListBox> , то не <xref:System.Windows.Controls.ListBox> выполняет виртуализацию <xref:System.Windows.Controls.ListBoxItem> объектов.

- Контейнеры элементов в <xref:System.Windows.Controls.ItemsControl> имеют разные типы. Например, объект <xref:System.Windows.Controls.Menu> , использующий <xref:System.Windows.Controls.Separator> объекты, не может реализовать повторное использование элементов, поскольку <xref:System.Windows.Controls.Menu> содержит объекты типа <xref:System.Windows.Controls.Separator> и <xref:System.Windows.Controls.MenuItem> .

- Значение <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> `false` .

- Значение <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> `false` .

Важным аспектом при виртуализации контейнеров элементов является наличие информации о дополнительном состоянии, связанной с контейнером элемента, принадлежащим этому элементу. В этом случае необходимо сохранить это дополнительное состояние. Например, у вас может быть элемент, содержащийся в <xref:System.Windows.Controls.Expander> элементе управления <xref:System.Windows.Controls.Expander.IsExpanded%2A> , а состояние привязано к контейнеру элемента, а не к самому элементу. При повторном использовании контейнера для нового элемента текущее значение <xref:System.Windows.Controls.Expander.IsExpanded%2A> используется для нового элемента. Кроме того, старый элемент теряет правильное <xref:System.Windows.Controls.Expander.IsExpanded%2A> значение.

В настоящее время элементы управления WPF не предоставляют встроенную поддержку виртуализации данных.

## <a name="container-recycling"></a>Повторное использование контейнера

Оптимизация виртуализации пользовательского интерфейса, добавленная в .NET Framework 3,5 с пакетом обновления 1 (SP1) для элементов управления, которые наследуют от, <xref:System.Windows.Controls.ItemsControl> — это также повышает производительность прокрутки. *container recycling,* Когда объект <xref:System.Windows.Controls.ItemsControl> , использующий виртуализацию пользовательского интерфейса, заполняется, он создает контейнер элементов для каждого элемента, который прокручивается в представление, и удаляет контейнер элемента для каждого элемента, который прокручивается из представления. *Повторное использование контейнера* позволяет элементу управления повторно использовать существующие контейнеры элементов для различных элементов данных, чтобы контейнеры элементов не создавались и уничтожались постоянно при прокрутке пользователем <xref:System.Windows.Controls.ItemsControl> . Можно включить повторное использование элементов, задав <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> для присоединенного свойства значение <xref:System.Windows.Controls.VirtualizationMode.Recycling> .

Любой <xref:System.Windows.Controls.ItemsControl> , поддерживающий виртуализацию, может использовать повторное использование контейнеров. Пример включения повторного использования контейнеров в см <xref:System.Windows.Controls.ListBox> . в разделе [улучшение производительности прокрутки списка](../controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).

## <a name="supporting-bidirectional-virtualization"></a>Поддержка двунаправленной виртуализации

<xref:System.Windows.Controls.VirtualizingStackPanel>предлагает встроенную поддержку виртуализации пользовательского интерфейса в одном направлении: по горизонтали или по вертикали. Если вы хотите использовать двунаправленную виртуализацию для элементов управления, необходимо реализовать пользовательскую панель, расширяющую <xref:System.Windows.Controls.VirtualizingStackPanel> класс. <xref:System.Windows.Controls.VirtualizingStackPanel>Класс предоставляет виртуальные методы, такие как <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A> , <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A> , <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A> и <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A> . Эти виртуальные методы позволяют обнаруживать изменения в видимой части списка и соответствующим образом реагировать на них.

## <a name="optimizing-templates"></a>Оптимизация шаблонов

Визуальное дерево содержит все визуальные элементы приложения. В дополнение к непосредственно созданным объектам оно также содержит объекты, возникшие из-за расширения шаблона. Например, при создании объект <xref:System.Windows.Controls.Button> также получает <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> <xref:System.Windows.Controls.ContentPresenter> объекты и в визуальном дереве. Без оптимизации шаблонов элементов управления может быть создано большое число дополнительных ненужных объектов в визуальном дереве. Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](../graphics-multimedia/wpf-graphics-rendering-overview.md).

## <a name="deferred-scrolling"></a>Отложенная прокрутка

По умолчанию, когда пользователь перетаскивает бегунок в полосе прокрутки, представление содержимого постоянно обновляется. Если скорость прокрутки в элементе управления низкая, рассмотрите возможность использования отложенной прокрутки. При отложенной прокрутке содержимое обновляется только в том случае, когда пользователь отпускает бегунок.

Чтобы реализовать отложенную прокрутку, присвойте <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> свойству значение `true` . <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A>является присоединенным свойством и может быть задано для <xref:System.Windows.Controls.ScrollViewer> и любого элемента управления, имеющего <xref:System.Windows.Controls.ScrollViewer> в своем шаблоне элемента управления.

## <a name="controls-that-implement-performance-features"></a>Элементы управления, реализующие функции производительности

В следующей таблице приведены общие элементы управления для отображения данных и их поддержка функций производительности. Сведения о том, как включать эти функции, см. в предыдущих разделах.

|Control|Виртуализация|Повторное использование контейнера|Отложенная прокрутка|
|-------------|--------------------|-------------------------|------------------------|
|<xref:System.Windows.Controls.ComboBox>|Можно включить|Можно включить|Можно включить|
|<xref:System.Windows.Controls.ContextMenu>|Можно включить|Можно включить|Можно включить|
|<xref:System.Windows.Controls.DocumentViewer>|Недоступно|Недоступно|Можно включить|
|<xref:System.Windows.Controls.ListBox>|По умолчанию|Можно включить|Можно включить|
|<xref:System.Windows.Controls.ListView>|По умолчанию|Можно включить|Можно включить|
|<xref:System.Windows.Controls.TreeView>|Можно включить|Можно включить|Можно включить|
|<xref:System.Windows.Controls.ToolBar>|Недоступно|Недоступно|Можно включить|

> [!NOTE]
> Пример включения виртуализации и повторного использования контейнеров в см. в <xref:System.Windows.Controls.TreeView> разделе [улучшение производительности TreeView](../controls/how-to-improve-the-performance-of-a-treeview.md).

## <a name="see-also"></a>См. также раздел

- [Макет](layout.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Привязка данных](optimizing-performance-data-binding.md)
- [Элементы управления](../controls/index.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Пошаговое руководство. Кэширование данных приложения WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
