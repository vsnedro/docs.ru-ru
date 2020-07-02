---
title: Практическое руководство. Реализация уведомления об изменении свойства
description: Включение свойств для автоматического уведомления источника привязки при изменении значения свойства в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: 6c298930b7b1f812e94ea6add8f53c67d3453530
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620785"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="5fb93-103">Практическое руководство. Реализация уведомления об изменении свойства</span><span class="sxs-lookup"><span data-stu-id="5fb93-103">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="5fb93-104">Чтобы обеспечить поддержку <xref:System.Windows.Data.BindingMode.OneWay> или <xref:System.Windows.Data.BindingMode.TwoWay> привязку, чтобы свойства целевого объекта привязки автоматически отражали динамические изменения источника привязки (например, чтобы панель предварительного просмотра обновлялась автоматически при редактировании пользователем формы), класс должен предоставить соответствующие уведомления об изменении свойств.</span><span class="sxs-lookup"><span data-stu-id="5fb93-104">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="5fb93-105">В этом примере показано, как создать класс, реализующий интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> .</span><span class="sxs-lookup"><span data-stu-id="5fb93-105">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb93-106">Пример</span><span class="sxs-lookup"><span data-stu-id="5fb93-106">Example</span></span>  
 <span data-ttu-id="5fb93-107">Для реализации необходимо <xref:System.ComponentModel.INotifyPropertyChanged> объявить <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> событие и создать `OnPropertyChanged` метод.</span><span class="sxs-lookup"><span data-stu-id="5fb93-107">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="5fb93-108">Затем для каждого свойства, которому потребуются уведомления об изменениях, вы вызываете `OnPropertyChanged` при каждом обновлении свойства.</span><span class="sxs-lookup"><span data-stu-id="5fb93-108">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="5fb93-109">Пример того `Person` , как можно использовать класс для поддержки <xref:System.Windows.Data.BindingMode.TwoWay> привязки, см. в разделе [Управление обновлением источника в текстовом поле](how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="5fb93-109">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb93-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5fb93-110">See also</span></span>

- [<span data-ttu-id="5fb93-111">Общие сведения об источниках привязки</span><span class="sxs-lookup"><span data-stu-id="5fb93-111">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="5fb93-112">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="5fb93-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5fb93-113">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="5fb93-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
