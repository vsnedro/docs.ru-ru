---
title: Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 2fe4458aa43144a9c29ed67fd7bee99a37fe1434
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739680"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged
Компонент <xref:System.Windows.Forms.BindingSource> автоматически обнаруживает изменения в источнике данных при реализации <xref:System.ComponentModel.INotifyPropertyChanged> типа, содержащегося в источнике данных, и вызывает <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> события при изменении значения свойства. Это обнаружение изменений полезно, поскольку элементы управления, связанные с автоматическим <xref:System.Windows.Forms.BindingSource> обновлением по мере изменения значений источника данных.  
  
> [!NOTE]
> Если источник данных реализует <xref:System.ComponentModel.INotifyPropertyChanged> и выполняются асинхронные операции, не следует вносить изменения в источник данных в фоновом потоке. Вместо этого рекомендуется считывать данные в фоновом потоке и объединять их в список в потоке пользовательского интерфейса.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан пример простой реализации интерфейса <xref:System.ComponentModel.INotifyPropertyChanged>. Также показано, как компонент <xref:System.Windows.Forms.BindingSource> автоматически передает изменения источника данных в связанный элемент управления, когда <xref:System.Windows.Forms.BindingSource> привязан к списку типа <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 При использовании атрибута `CallerMemberName` в вызовах метода `NotifyPropertyChanged` нет необходимости указывать имя свойства в качестве строкового аргумента. Для получения дополнительной информации, см. [Caller Information (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md) [Caller Information (C#)](../../../csharp/language-reference/attributes/caller-information.md)  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- Ссылки на сборки системы, System.Data, System.Drawing и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [Компонент BindingSource](bindingsource-component.md)
- [Практическое руководство. Уведомление об изменении данных с использованием метода ResetItem компонента BindingSource](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
