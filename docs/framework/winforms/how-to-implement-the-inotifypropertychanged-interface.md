---
title: Практическое руководство. Реализация интерфейса INotifyPropertyChanged
description: Узнайте, как реализовать интерфейс INotifyPropertyChanged для бизнес-объектов, которые используются в Windows Forms привязке данных.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 83d2ef32787d2dbcd877bc77dcede10111098f8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619272"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Практическое руководство. Реализация интерфейса INotifyPropertyChanged
В следующем примере кода показано, как реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс. Реализуйте этот интерфейс для бизнес-объектов, которые используются в Windows Forms привязке данных. При реализации интерфейс взаимодействует с привязанным элементом управления изменением свойства в бизнес-объекте.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Применение шаблона PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)
- [Привязка данных Windows Forms](windows-forms-data-binding.md)
- [Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md)
- [Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms](change-notification-in-windows-forms-data-binding.md)
