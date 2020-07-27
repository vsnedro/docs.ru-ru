---
title: Как группировать, сортировать и фильтровать данные в элементе управления DataGrid
description: Узнайте, как привязать Windows Presentation Foundation элемент управления DataGrid к CollectionView, поддерживающему группирование, сортировку и фильтрацию данных в представлениях.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 072e5a104a91faa40bb54f2a3fc4ed6188e1112e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167673"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Как группировать, сортировать и фильтровать данные в элементе управления DataGrid

Часто бывает удобно просматривать данные в, <xref:System.Windows.Controls.DataGrid> используя группировку, сортировку и фильтрацию данных. Чтобы сгруппировать, сортировать и фильтровать данные в <xref:System.Windows.Controls.DataGrid> , привяжите их к <xref:System.Windows.Data.CollectionView> , который поддерживает эти функции. Затем можно работать с данными в, <xref:System.Windows.Data.CollectionView> не влияя на базовые исходные данные. Изменения в представлении коллекции отражаются в <xref:System.Windows.Controls.DataGrid> пользовательском интерфейсе.

<xref:System.Windows.Data.CollectionView>Класс предоставляет функции группирования и сортировки для источника данных, реализующего <xref:System.Collections.IEnumerable> интерфейс. <xref:System.Windows.Data.CollectionViewSource>Класс позволяет задавать свойства <xref:System.Windows.Data.CollectionView> из XAML.

В этом примере коллекция `Task` объектов привязана к <xref:System.Windows.Data.CollectionViewSource> . <xref:System.Windows.Data.CollectionViewSource>Используется в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.DataGrid> . Группирование, сортировка и фильтрация выполняются в <xref:System.Windows.Data.CollectionViewSource> и отображаются в <xref:System.Windows.Controls.DataGrid> пользовательском интерфейсе.

![Сгруппированные данные в элементе управления DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Сгруппированные данные в элементе управления DataGrid

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Использование CollectionViewSource в качестве ItemsSource

Для группирования, сортировки и фильтрации данных в <xref:System.Windows.Controls.DataGrid> элементе управления необходимо привязать <xref:System.Windows.Controls.DataGrid> к элементу <xref:System.Windows.Data.CollectionView> , который поддерживает эти функции. В этом примере <xref:System.Windows.Controls.DataGrid> Привязка привязана к <xref:System.Windows.Data.CollectionViewSource> объекту, который предоставляет эти функции для <xref:System.Collections.Generic.List%601> `Task` объектов.

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>Привязка элемента управления DataGrid к CollectionViewSource

1. Создайте коллекцию данных, которая реализует <xref:System.Collections.IEnumerable> интерфейс.

    При использовании <xref:System.Collections.Generic.List%601> для создания коллекции следует создать новый класс, наследующий от класса, <xref:System.Collections.Generic.List%601> а не экземпляр <xref:System.Collections.Generic.List%601> . Это позволяет привязывать данные к коллекции в XAML.

    > [!NOTE]
    > Объекты в коллекции должны реализовывать <xref:System.ComponentModel.INotifyPropertyChanged> измененный интерфейс и интерфейс, чтобы <xref:System.ComponentModel.IEditableObject> <xref:System.Windows.Controls.DataGrid> обеспечить правильную реакцию на изменения свойств и их изменение. Дополнительные сведения см. в разделе [Реализация уведомления об изменении свойств](../data/how-to-implement-property-change-notification.md).

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. В XAML создайте экземпляр класса Collection и задайте [директиву x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md).

3. В XAML создайте экземпляр <xref:System.Windows.Data.CollectionViewSource> класса, установите [директиву x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md)и задайте для экземпляра класса коллекции значение <xref:System.Windows.Data.CollectionViewSource.Source%2A> .

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. Создайте экземпляр <xref:System.Windows.Controls.DataGrid> класса и присвойте <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойству значение <xref:System.Windows.Data.CollectionViewSource> .

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. Для доступа к <xref:System.Windows.Data.CollectionViewSource> из кода используйте <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> метод, чтобы получить ссылку на <xref:System.Windows.Data.CollectionViewSource> .

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>Группирование элементов в элементе управления DataGrid

Чтобы указать, как группируются элементы в <xref:System.Windows.Controls.DataGrid> , используйте <xref:System.Windows.Data.PropertyGroupDescription> тип для группирования элементов в представлении исходного кода.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Группирование элементов в элементе управления DataGrid с помощью XAML

1. Создайте объект <xref:System.Windows.Data.PropertyGroupDescription> , указывающий свойство для группировки. Свойство можно указать в XAML или в коде.

   1. В XAML присвойте <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> свойству имя свойства, по которому будет группироваться.

   2. В коде передайте имя свойства, по которому выполняется группирование, в конструктор.

2. Добавьте в <xref:System.Windows.Data.PropertyGroupDescription> <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> коллекцию.

3. Добавьте дополнительные экземпляры <xref:System.Windows.Data.PropertyGroupDescription> в коллекцию, <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> чтобы добавить дополнительные уровни группирования.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. Чтобы удалить группу, удалите ее <xref:System.Windows.Data.PropertyGroupDescription> из <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> коллекции.

5. Чтобы удалить все группы, вызовите <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> метод <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> коллекции.

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

Если элементы группируются в <xref:System.Windows.Controls.DataGrid> , можно определить <xref:System.Windows.Controls.GroupStyle> , определяющую внешний вид каждой группы. Вы примените, <xref:System.Windows.Controls.GroupStyle> добавив его в <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> коллекцию DataGrid. При наличии нескольких уровней группировки можно применить различные стили к каждому уровню группировки. Стили применяются в том порядке, в котором они определены. Например, если определить два стиля, первый будет применяться к группам строк верхнего уровня. Второй стиль будет применен ко всем группам строк на втором уровне и ниже. Объект <xref:System.Windows.FrameworkElement.DataContext%2A> класса, <xref:System.Windows.Controls.GroupStyle> <xref:System.Windows.Data.CollectionViewGroup> представленный группой.

### <a name="to-change-the-appearance-of-row-group-headers"></a>Изменение внешнего вида заголовков групп строк

1. Создайте объект <xref:System.Windows.Controls.GroupStyle> , определяющий внешний вид группы строк.

2. Разместите <xref:System.Windows.Controls.GroupStyle> внутри `<DataGrid.GroupStyle>` тегов.

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>Сортировка элементов в элементе управления DataGrid

Чтобы указать порядок сортировки элементов в <xref:System.Windows.Controls.DataGrid> , используйте <xref:System.ComponentModel.SortDescription> тип для сортировки элементов в представлении исходного кода.

### <a name="to-sort-items-in-a-datagrid"></a>Сортировка элементов в элементе управления DataGrid

1. Создайте объект <xref:System.ComponentModel.SortDescription> , указывающий свойство, по которому выполняется сортировка. Свойство можно указать в XAML или в коде.

    1. В XAML присвойте <xref:System.ComponentModel.SortDescription.PropertyName%2A> свойству имя свойства, по которому будет выполняться сортировка.

    2. В коде передайте имя свойства для сортировки и в <xref:System.ComponentModel.ListSortDirection> конструктор.

2. Добавьте в <xref:System.ComponentModel.SortDescription> <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> коллекцию.

3. Добавьте дополнительные экземпляры <xref:System.ComponentModel.SortDescription> в <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> коллекцию для сортировки по дополнительным свойствам.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>Фильтрация элементов в элементе управления DataGrid

Чтобы отфильтровать элементы в <xref:System.Windows.Controls.DataGrid> с помощью <xref:System.Windows.Data.CollectionViewSource> , необходимо предоставить логику фильтрации в обработчике <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> события.

### <a name="to-filter-items-in-a-datagrid"></a>Фильтрация элементов в элементе управления DataGrid

1. Добавьте обработчик для <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> события.

2. В <xref:System.Windows.Data.CollectionViewSource.Filter> обработчике событий определите логику фильтрации.

    Фильтр будет применяться при каждом обновлении представления.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

Кроме того, можно отфильтровать элементы в <xref:System.Windows.Controls.DataGrid> , создав метод, предоставляющий логику фильтрации и установив <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> свойство для применения фильтра. Пример этого метода см. в разделе [Фильтрация данных в представлении](../data/how-to-filter-data-in-a-view.md).

## <a name="example"></a>Пример

В следующем примере демонстрируется группирование, сортировка и фильтрация `Task` данных в <xref:System.Windows.Data.CollectionViewSource> и отображение сгруппированных, отсортированных и отфильтрованных `Task` данных в <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Data.CollectionViewSource>Используется в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.DataGrid> . Группирование, сортировка и фильтрация выполняются в <xref:System.Windows.Data.CollectionViewSource> и отображаются в <xref:System.Windows.Controls.DataGrid> пользовательском интерфейсе.

Чтобы протестировать этот пример, необходимо изменить имя Дгграупсортфилтерексампле в соответствии с именем проекта. При использовании Visual Basic необходимо изменить имя класса на <xref:System.Windows.Window> следующее.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>См. также раздел

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Создание и привязка к ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [Фильтрация данных в представлении](../data/how-to-filter-data-in-a-view.md)
- [Сортировка данных в представлении](../data/how-to-sort-data-in-a-view.md)
- [Сортировка и группирование данных с помощью представления в XAML](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
