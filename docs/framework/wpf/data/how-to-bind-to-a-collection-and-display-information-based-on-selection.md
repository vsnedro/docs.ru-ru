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
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="c9e33-103">Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента</span><span class="sxs-lookup"><span data-stu-id="c9e33-103">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="c9e33-104">В простом сценарии «основной/подробности» имеется привязка к данным, <xref:System.Windows.Controls.ItemsControl> например <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="c9e33-104">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="c9e33-105">На основе выбора пользователя отображаются дополнительные сведения о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="c9e33-105">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="c9e33-106">В этом примере показано, как реализовать этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="c9e33-106">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9e33-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c9e33-107">Example</span></span>  
 <span data-ttu-id="c9e33-108">В этом примере `People` — это класс <xref:System.Collections.ObjectModel.ObservableCollection%601> `Person` класса.</span><span class="sxs-lookup"><span data-stu-id="c9e33-108">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="c9e33-109">Этот `Person` класс содержит три свойства: `FirstName` , `LastName` и `HomeTown` , все типы `string` .</span><span class="sxs-lookup"><span data-stu-id="c9e33-109">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="c9e33-110">В <xref:System.Windows.Controls.ContentControl> компоненте используются следующие <xref:System.Windows.DataTemplate> Параметры, определяющие, как `Person` представляется информация о представлении.</span><span class="sxs-lookup"><span data-stu-id="c9e33-110">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="c9e33-111">Ниже приведен снимок экрана, в котором создается пример.</span><span class="sxs-lookup"><span data-stu-id="c9e33-111">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="c9e33-112"><xref:System.Windows.Controls.ContentControl>Отображает другие свойства выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="c9e33-112">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="c9e33-113">![Привязка к коллекции](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="c9e33-113">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="c9e33-114">В этом примере необходимо обратить внимание на два момента:</span><span class="sxs-lookup"><span data-stu-id="c9e33-114">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="c9e33-115"><xref:System.Windows.Controls.ListBox>И <xref:System.Windows.Controls.ContentControl> привязку к одному и тому же источнику.</span><span class="sxs-lookup"><span data-stu-id="c9e33-115">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="c9e33-116"><xref:System.Windows.Data.Binding.Path%2A>Свойства обеих привязок не указаны, так как оба элемента управления привязаны ко всему объекту коллекции.</span><span class="sxs-lookup"><span data-stu-id="c9e33-116">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="c9e33-117">Чтобы это работало, необходимо задать <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> для свойства значение `true` .</span><span class="sxs-lookup"><span data-stu-id="c9e33-117">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="c9e33-118">Задание этого свойства гарантирует, что выбранный элемент всегда будет установлен в качестве <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> .</span><span class="sxs-lookup"><span data-stu-id="c9e33-118">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="c9e33-119">Кроме того, если объект <xref:System.Windows.Controls.ListBox> получает данные из <xref:System.Windows.Data.CollectionViewSource> , он автоматически синхронизирует выбор и валют.</span><span class="sxs-lookup"><span data-stu-id="c9e33-119">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="c9e33-120">Обратите внимание, что `Person` класс переопределяет `ToString` метод следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c9e33-120">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="c9e33-121">По умолчанию <xref:System.Windows.Controls.ListBox> вызывает `ToString` и отображает строковое представление каждого объекта в привязанной коллекции.</span><span class="sxs-lookup"><span data-stu-id="c9e33-121">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="c9e33-122">Поэтому каждый из них `Person` отображается как имя в <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="c9e33-122">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="c9e33-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c9e33-123">See also</span></span>

- [<span data-ttu-id="c9e33-124">Использование шаблона "основной/подробности" с иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="c9e33-124">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="c9e33-125">Использование шаблона "основной/подробности" с иерархическими XML-данными</span><span class="sxs-lookup"><span data-stu-id="c9e33-125">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="c9e33-126">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="c9e33-126">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="c9e33-127">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="c9e33-127">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="c9e33-128">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="c9e33-128">How-to Topics</span></span>](data-binding-how-to-topics.md)
