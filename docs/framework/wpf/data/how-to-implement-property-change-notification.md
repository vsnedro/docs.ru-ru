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
# <a name="how-to-implement-property-change-notification"></a>Практическое руководство. Реализация уведомления об изменении свойства
Чтобы обеспечить поддержку <xref:System.Windows.Data.BindingMode.OneWay> или <xref:System.Windows.Data.BindingMode.TwoWay> привязку, чтобы свойства целевого объекта привязки автоматически отражали динамические изменения источника привязки (например, чтобы панель предварительного просмотра обновлялась автоматически при редактировании пользователем формы), класс должен предоставить соответствующие уведомления об изменении свойств. В этом примере показано, как создать класс, реализующий интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> .  
  
## <a name="example"></a>Пример  
 Для реализации необходимо <xref:System.ComponentModel.INotifyPropertyChanged> объявить <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> событие и создать `OnPropertyChanged` метод. Затем для каждого свойства, которому потребуются уведомления об изменениях, вы вызываете `OnPropertyChanged` при каждом обновлении свойства.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Пример того `Person` , как можно использовать класс для поддержки <xref:System.Windows.Data.BindingMode.TwoWay> привязки, см. в разделе [Управление обновлением источника в текстовом поле](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения об источниках привязки](binding-sources-overview.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Практические руководства](data-binding-how-to-topics.md)
