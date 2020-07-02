---
title: Практическое руководство. Сортировка и группировка данных с помощью представления в XAML
description: Узнайте, как создать представление коллекции данных для группирования, сортировки и фильтрации в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: a4f8e2de9345dba8e4ea0d3a16a32d57a9adb55c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621682"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="e7c76-103">Практическое руководство. Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="e7c76-103">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="e7c76-104">В этом примере показано, как создать представление коллекции данных в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7c76-104">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="e7c76-105">Представления обеспечивают функциональные возможности группирования, сортировки, фильтрации и понятия текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="e7c76-105">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7c76-106">Пример</span><span class="sxs-lookup"><span data-stu-id="e7c76-106">Example</span></span>  
 <span data-ttu-id="e7c76-107">В следующем примере статический ресурс с именем *Places* определяется как коллекция объектов *Place* , в которых каждый объект- *место* состоит из названия города и состояния.</span><span class="sxs-lookup"><span data-stu-id="e7c76-107">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="e7c76-108">Префикс *src* сопоставляется с пространством *имен, в котором определены источники данных* .</span><span class="sxs-lookup"><span data-stu-id="e7c76-108">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="e7c76-109">Префикс *SCM* сопоставляется с `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` и *dat* Maps `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` .</span><span class="sxs-lookup"><span data-stu-id="e7c76-109">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="e7c76-110">В следующем примере создается представление коллекции данных, которая сортируется по названию города и группируются по состоянию.</span><span class="sxs-lookup"><span data-stu-id="e7c76-110">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="e7c76-111">Представление может быть источником привязки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e7c76-111">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="e7c76-112">Для привязок к XML-данным, определенным в <xref:System.Windows.Data.XmlDataProvider> ресурсе, перед именем XML следует указывать символ @.</span><span class="sxs-lookup"><span data-stu-id="e7c76-112">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="e7c76-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e7c76-113">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="e7c76-114">Получение представления по умолчанию для коллекции данных</span><span class="sxs-lookup"><span data-stu-id="e7c76-114">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="e7c76-115">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="e7c76-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="e7c76-116">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="e7c76-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
