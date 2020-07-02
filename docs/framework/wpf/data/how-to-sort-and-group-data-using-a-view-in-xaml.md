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
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Практическое руководство. Сортировка и группировка данных с помощью представления в XAML
В этом примере показано, как создать представление коллекции данных в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Представления обеспечивают функциональные возможности группирования, сортировки, фильтрации и понятия текущего элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере статический ресурс с именем *Places* определяется как коллекция объектов *Place* , в которых каждый объект- *место* состоит из названия города и состояния. Префикс *src* сопоставляется с пространством *имен, в котором определены источники данных* . Префикс *SCM* сопоставляется с `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` и *dat* Maps `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` .  
  
 В следующем примере создается представление коллекции данных, которая сортируется по названию города и группируются по состоянию.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Представление может быть источником привязки, как показано в следующем примере:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Для привязок к XML-данным, определенным в <xref:System.Windows.Data.XmlDataProvider> ресурсе, перед именем XML следует указывать символ @.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.CollectionViewSource>
- [Получение представления по умолчанию для коллекции данных](how-to-get-the-default-view-of-a-data-collection.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Практические руководства](data-binding-how-to-topics.md)
