---
title: Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента
description: Выполните приведенный ниже пример, чтобы узнать, как выполнить привязку к коллекции и отобразить сведения на основе выбора в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: fb8757ee6818a2812308a0a132fa9d06951ad52e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619615"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента
В простом сценарии «основной/подробности» имеется привязка к данным, <xref:System.Windows.Controls.ItemsControl> например <xref:System.Windows.Controls.ListBox> . На основе выбора пользователя отображаются дополнительные сведения о выбранном элементе. В этом примере показано, как реализовать этот сценарий.  
  
## <a name="example"></a>Пример  
 В этом примере `People` — это класс <xref:System.Collections.ObjectModel.ObservableCollection%601> `Person` класса. Этот `Person` класс содержит три свойства: `FirstName` , `LastName` и `HomeTown` , все типы `string` .  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 В <xref:System.Windows.Controls.ContentControl> компоненте используются следующие <xref:System.Windows.DataTemplate> Параметры, определяющие, как `Person` представляется информация о представлении.  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Ниже приведен снимок экрана, в котором создается пример. <xref:System.Windows.Controls.ContentControl>Отображает другие свойства выбранного человека.  
  
 ![Привязка к коллекции](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 В этом примере необходимо обратить внимание на два момента:  
  
1. <xref:System.Windows.Controls.ListBox>И <xref:System.Windows.Controls.ContentControl> привязку к одному и тому же источнику. <xref:System.Windows.Data.Binding.Path%2A>Свойства обеих привязок не указаны, так как оба элемента управления привязаны ко всему объекту коллекции.  
  
2. Чтобы это работало, необходимо задать <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> для свойства значение `true` . Задание этого свойства гарантирует, что выбранный элемент всегда будет установлен в качестве <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> . Кроме того, если объект <xref:System.Windows.Controls.ListBox> получает данные из <xref:System.Windows.Data.CollectionViewSource> , он автоматически синхронизирует выбор и валют.  
  
 Обратите внимание, что `Person` класс переопределяет `ToString` метод следующим образом. По умолчанию <xref:System.Windows.Controls.ListBox> вызывает `ToString` и отображает строковое представление каждого объекта в привязанной коллекции. Поэтому каждый из них `Person` отображается как имя в <xref:System.Windows.Controls.ListBox> .  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>См. также

- [Использование шаблона "основной/подробности" с иерархическими данными](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Использование шаблона "основной/подробности" с иерархическими XML-данными](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о шаблонах данных](data-templating-overview.md)
- [Практические руководства](data-binding-how-to-topics.md)
