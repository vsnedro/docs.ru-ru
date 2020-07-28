---
title: Общие сведения об элементе управления ScrollViewer
description: Сведения об элементе управления ScrollViewer, который обеспечивает прокрутку содержимого в Windows Presentation Foundation приложениях. См. примеры использования.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 1ef680bb004315a2b523814714d5533535d044e5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164645"
---
# <a name="scrollviewer-overview"></a>Общие сведения об элементе управления ScrollViewer
Часто содержимое в пользовательском интерфейсе занимает больше места, чем вмещает область отображения на экране компьютера. <xref:System.Windows.Controls.ScrollViewer>Элемент управления предоставляет удобный способ для включения прокрутки содержимого в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложениях. В этом разделе описывается <xref:System.Windows.Controls.ScrollViewer> элемент и приводится несколько примеров использования.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>Элемент управления ScrollViewer  
 Есть два предопределенных элемента, которые позволяют выполнять прокрутку в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложениях: <xref:System.Windows.Controls.Primitives.ScrollBar> и <xref:System.Windows.Controls.ScrollViewer> . <xref:System.Windows.Controls.ScrollViewer>Элемент управления инкапсулирует горизонтальные и вертикальные <xref:System.Windows.Controls.Primitives.ScrollBar> элементы и контейнер содержимого (например, <xref:System.Windows.Controls.Panel> элемент) для отображения других видимых элементов в прокручиваемой области. Чтобы использовать <xref:System.Windows.Controls.Primitives.ScrollBar> элемент для прокрутки содержимого, необходимо создать пользовательский объект. Однако элемент можно использовать отдельно, <xref:System.Windows.Controls.ScrollViewer> так как он является составным элементом управления, который инкапсулирует <xref:System.Windows.Controls.Primitives.ScrollBar> функциональность.  
  
 <xref:System.Windows.Controls.ScrollViewer>Элемент управления реагирует на команды мыши и клавиатуры и определяет многочисленные методы, с помощью которых прокрутка содержимого осуществляется с помощью заранее заданных приращений. Событие можно использовать <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> для обнаружения изменений в <xref:System.Windows.Controls.ScrollViewer> состоянии.  
  
 <xref:System.Windows.Controls.ScrollViewer>Может иметь только один дочерний элемент, как правило, с <xref:System.Windows.Controls.Panel> элементом, на котором может размещаться <xref:System.Windows.Controls.Panel.Children%2A> Коллекция элементов. <xref:System.Windows.Controls.ContentPresenter.Content%2A>Свойство определяет единственного потомка <xref:System.Windows.Controls.ScrollViewer> .  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>Физическая и Логическая прокрутка  
 Физическая прокрутка используется для прокрутки на предопределенное приращение, которое обычно является значением, объявленным в пикселях. Логическая прокрутка используется для прокрутки к следующему элементу в логическом дереве. Физическая прокрутка — это поведение прокрутки по умолчанию для большинства <xref:System.Windows.Controls.Panel> элементов. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает оба типа прокрутки.  
  
#### <a name="the-iscrollinfo-interface"></a>Интерфейс IScrollInfo  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>Интерфейс представляет главную область прокрутки внутри <xref:System.Windows.Controls.ScrollViewer> или производного элемента управления. Интерфейс определяет свойства прокрутки и методы, которые могут быть реализованы <xref:System.Windows.Controls.Panel> элементами, требующими прокрутки логической единицей, а не физическим инкрементом. Приведение экземпляра <xref:System.Windows.Controls.Primitives.IScrollInfo> к производному <xref:System.Windows.Controls.Panel> , а затем использование его методов прокрутки предоставляет удобный способ прокрутки к следующей логической единице в дочерней коллекции, а не на инкременте пикселя. По умолчанию <xref:System.Windows.Controls.ScrollViewer> элемент управления поддерживает прокрутку по физическим единицам.  
  
 <xref:System.Windows.Controls.StackPanel>и <xref:System.Windows.Controls.VirtualizingStackPanel> реализуют <xref:System.Windows.Controls.Primitives.IScrollInfo> и изначально поддерживают логическую прокрутку. Для элементов управления макета, которые изначально поддерживают логическую прокрутку, можно обеспечить физическую прокрутку, заключив ведущий <xref:System.Windows.Controls.Panel> элемент в <xref:System.Windows.Controls.ScrollViewer> и присвоив <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> свойству значение `false` .  
  
 В следующем примере кода показано, как привести экземпляр к типу <xref:System.Windows.Controls.Primitives.IScrollInfo> <xref:System.Windows.Controls.StackPanel> и использовать методы прокрутки содержимого ( <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> и <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> ), определенные интерфейсом.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>Определение и использование элемента ScrollViewer  
 В следующем примере создается <xref:System.Windows.Controls.ScrollViewer> в окне, которое содержит некоторый текст и прямоугольник. <xref:System.Windows.Controls.Primitives.ScrollBar>элементы отображаются, только если они необходимы. При изменении размера окна <xref:System.Windows.Controls.Primitives.ScrollBar> элементы отображаются и исчезают из-за обновленных значений <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> свойств и.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>Стили элемента управления ScrollViewer  
 Как и все элементы управления в Windows Presentation Foundation, <xref:System.Windows.Controls.ScrollViewer> для изменения поведения отрисовки элемента управления по умолчанию можно использовать стиль. Дополнительные сведения о стилях элементов управления см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>Разбивка документов на страницы  
 Альтернативой прокрутке содержимого документа является контейнер документа, поддерживающий разбиение на страницы. <xref:System.Windows.Documents.FlowDocument>предназначен для документов, предназначенных для размещения в элементе управления просмотром, например <xref:System.Windows.Controls.FlowDocumentPageViewer> , который поддерживает разбивка содержимое на нескольких страницах, предотвращая необходимость прокрутки. <xref:System.Windows.Controls.DocumentViewer>предоставляет решение для просмотра <xref:System.Windows.Documents.FixedDocument> содержимого, которое использует традиционную прокрутку для отображения содержимого вне области отображения.  
  
 Дополнительные сведения о форматах документа и параметрах представления см. в разделе [Документы в WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Как создать средство просмотра прокрутки](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Документы в WPF](../advanced/documents-in-wpf.md)
- [Стили и шаблоны элемента ScrollBar](scrollbar-styles-and-templates.md)
- [Элементы управления](../advanced/optimizing-performance-controls.md)
