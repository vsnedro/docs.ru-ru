---
title: Параметры изменения размеров элемента управления DataGrid
description: Узнайте, как задать размер отдельных строк и столбцов в элементе управления Windows Presentation Foundation DataGrid, чтобы его содержимое или конкретные значения были заданы.
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0f10e385cbf18a26989614363ca6cd9f92bc83ec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164740"
---
# <a name="sizing-options-in-the-datagrid-control"></a>Параметры изменения размеров элемента управления DataGrid
Для управления <xref:System.Windows.Controls.DataGrid> самими размерами доступны различные параметры. Для <xref:System.Windows.Controls.DataGrid> , и отдельные строки и столбцы в <xref:System.Windows.Controls.DataGrid> можно установить автоматическое присвоение размера их содержимого или могут быть установлены в определенные значения. По умолчанию <xref:System.Windows.Controls.DataGrid> размер увеличивается и сжимается в соответствии с размером содержимого.  
  
## <a name="sizing-the-datagrid"></a>Изменение размера элемента управления DataGrid  
  
### <a name="cautions-when-using-automatic-sizing"></a>Предостережения при использовании автоматического изменения размера  
 По умолчанию для <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> свойств и объекта <xref:System.Windows.Controls.DataGrid> задано значение <xref:System.Double.NaN?displayProperty=nameWithType> (" `Auto` " в XAML), а параметр будет изменяться <xref:System.Windows.Controls.DataGrid> на размер его содержимого.  
  
 При помещении в контейнер, который не ограничивает размер дочерних элементов, например <xref:System.Windows.Controls.Canvas> или <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.DataGrid> растягивается за видимыми границами контейнера, а полосы прокрутки не будут отображаться. Это условие влияет на удобство использования и производительность.  
  
 При привязке к набору данных, если параметр <xref:System.Windows.FrameworkElement.Height%2A> объекта <xref:System.Windows.Controls.DataGrid> не ограничен, он будет по-прежнему добавлять строку для каждого элемента данных в связанном наборе данных. Это может привести к <xref:System.Windows.Controls.DataGrid> увеличению числа видимых границ приложения при добавлении строк. В <xref:System.Windows.Controls.DataGrid> этом случае полосы прокрутки не будут отображаться, так как по- <xref:System.Windows.FrameworkElement.Height%2A> прежнему будет увеличиваться в соответствии с новыми строками.  
  
 Объект создается для каждой строки в <xref:System.Windows.Controls.DataGrid> . Если вы работаете с большим набором данных и разрешаете <xref:System.Windows.Controls.DataGrid> автоматически изменять размер, создание большого количества объектов может повлиять на производительность приложения.  
  
 Чтобы избежать этих проблем при работе с большими наборами данных, рекомендуется явно задать параметр <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.DataGrid> или поместить его в контейнер, который будет ограничивать его <xref:System.Windows.FrameworkElement.Height%2A> , например <xref:System.Windows.Controls.Grid> . Если <xref:System.Windows.FrameworkElement.Height%2A> ограничение ограничено, то <xref:System.Windows.Controls.DataGrid> будут созданы только те строки, которые помещаются в указанном <xref:System.Windows.FrameworkElement.Height%2A> виде, и будут перезапускать строки по мере необходимости для вывода новых данных.  
  
### <a name="setting-the-datagrid-size"></a>Установка размера DataGrid  
 <xref:System.Windows.Controls.DataGrid>Можно задать автоматическое изменение размера в пределах заданных границ, а также <xref:System.Windows.Controls.DataGrid> задать определенный размер. В следующей таблице показаны свойства, которые можно задать для управления <xref:System.Windows.Controls.DataGrid> размером.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Задает определенную высоту для <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Задает верхнюю границу высоты объекта <xref:System.Windows.Controls.DataGrid> . Значение <xref:System.Windows.Controls.DataGrid> будет увеличиваться по вертикали до достижения этой высоты.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Задает нижнюю границу высоты объекта <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>Будет сжиматься по вертикали до достижения этой высоты.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Задает определенную ширину для <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Задает верхнюю границу ширины элемента <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>Будет увеличиваться по горизонтали до достижения этой ширины.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Задает нижнюю границу ширины элемента <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>Будет сжиматься по горизонтали до достижения этой ширины.|  
  
## <a name="sizing-rows-and-row-headers"></a>Изменение размера строк и заголовков строк  
  
### <a name="datagrid-rows"></a>Строки DataGrid  
 По умолчанию <xref:System.Windows.Controls.DataGrid> свойству строки присваивается <xref:System.Windows.FrameworkElement.Height%2A> значение <xref:System.Double.NaN?displayProperty=nameWithType> (" `Auto` " в XAML), а высота строки расширяется до размера ее содержимого. Высоту всех строк в <xref:System.Windows.Controls.DataGrid> можно задать, задав <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> свойство. Пользователи могут изменять высоту строки, перетаскивая разделители заголовков строк.  
  
### <a name="datagrid-row-headers"></a>Заголовки строк DataGrid  
 Для вывода заголовков строк <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> свойство должно иметь значение <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> или <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType> . По умолчанию заголовки строк отображаются, и их размер автоматически изменяется в соответствии с содержимым. Заголовку строки можно присвоить определенную ширину, задав <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> свойство.  
  
## <a name="sizing-columns-and-column-headers"></a>Изменение размеров столбцов и заголовков столбцов  
  
### <a name="datagrid-columns"></a>Столбцы DataGrid  
 <xref:System.Windows.Controls.DataGrid>Использует значения <xref:System.Windows.Controls.DataGridLength> <xref:System.Windows.Controls.DataGridLengthUnitType> структуры и для указания абсолютного или автоматического режима изменения размеров.  
  
 В следующей таблице показаны значения, предоставляемые <xref:System.Windows.Controls.DataGridLengthUnitType> структурой.  
  
|Имя|Описание|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|По умолчанию в режиме автоматического изменения размеров <xref:System.Windows.Controls.DataGrid> столбцы зависят от содержимого ячеек и заголовков столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|Режим автоматического изменения размеров на основе ячеек определяет размеры <xref:System.Windows.Controls.DataGrid> столбцов на основе содержимого ячеек в столбце, не включая заголовки столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|Режим автоматического изменения размеров на основе заголовков определяет размеры <xref:System.Windows.Controls.DataGrid> столбцов, основанных только на содержимом заголовков столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|В режиме изменения размеров на основе пикселов размеры <xref:System.Windows.Controls.DataGrid> столбцов основаны на указанном числовом значении.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|Режим изменения размера в звездах используется для распределения доступного места по взвешенным пропорциям.<br /><br /> В XAML значения типа "звезда" выражаются как n *, где n представляет числовое значение. 1 \* эквивалентен \* . Например, если два столбца в <xref:System.Windows.Controls.DataGrid> имеют ширину \* и 2 \* , то первый столбец будет иметь одну часть доступного пространства, а второй столбец будет иметь две части доступного пространства.|  
  
 <xref:System.Windows.Controls.DataGridLengthConverter>Класс может использоваться для преобразования данных между числовыми или строковыми значениями и <xref:System.Windows.Controls.DataGridLength> значениями.  
  
 По умолчанию <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> свойство имеет значение <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A> , а <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> свойство имеет значение <xref:System.Windows.Controls.DataGridLength.Auto%2A> . Если для режима изменения размера задано значение <xref:System.Windows.Controls.DataGridLength.Auto%2A> или <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A> , столбцы будут увеличиваться до ширины их широкого видимого содержимого. При прокрутке эти режимы изменения размеров приведут к тому, что столбцы будут расширяться, если содержимое, превышающее текущий размер столбца, будет прокручиваться в представлении. Столбец не будет сжиматься после прокрутки содержимого из представления.  
  
 Для столбцов в <xref:System.Windows.Controls.DataGrid> можно также задать автоматическое изменение размера только в пределах указанных границ, а для столбцов можно задать определенный размер. В следующей таблице показаны свойства, которые можно задать для управления размером столбцов.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Задает верхнюю границу для всех столбцов в <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Задает верхнюю границу для отдельного столбца. Переопределяет <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Задает нижнюю границу для всех столбцов в <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Задает нижнюю границу для отдельного столбца. Переопределяет <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Задает определенную ширину для всех столбцов в <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Задает определенную ширину для отдельного столбца. Переопределяет <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>Заголовки столбцов DataGrid  
 По умолчанию <xref:System.Windows.Controls.DataGrid> заголовки столбцов отображаются. Чтобы скрыть заголовки столбцов, <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> свойство должно иметь значение <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> или <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType> . По умолчанию при отображении заголовков столбцов их размер автоматически изменяется в соответствии с содержимым. Заголовку столбца можно присвоить определенную высоту, задав <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> свойство.  
  
### <a name="resizing-with-the-mouse"></a>Изменение размера с помощью мыши  
 Пользователи могут изменять размер <xref:System.Windows.Controls.DataGrid> строк и столбцов, перетаскивая разделители заголовков строк или столбцов. <xref:System.Windows.Controls.DataGrid>Также поддерживает автоматическое изменение размера строк и столбцов, дважды щелкнув разделитель заголовков строк или столбцов. Чтобы запретить пользователю изменять размер определенных столбцов, установите <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> свойство в значение `false` для отдельных столбцов. Чтобы запретить пользователям изменять размер всех столбцов, присвойте <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> свойству значение `false` . Чтобы запретить пользователям изменять размер всех строк, присвойте <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> свойству значение `false` .  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGridColumn>
- <xref:System.Windows.Controls.DataGridLength>
- <xref:System.Windows.Controls.DataGridLengthConverter>
