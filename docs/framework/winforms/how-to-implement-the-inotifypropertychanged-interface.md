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
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="6ed22-103">Практическое руководство. Реализация интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="6ed22-103">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="6ed22-104">В следующем примере кода показано, как реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6ed22-104">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="6ed22-105">Реализуйте этот интерфейс для бизнес-объектов, которые используются в Windows Forms привязке данных.</span><span class="sxs-lookup"><span data-stu-id="6ed22-105">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="6ed22-106">При реализации интерфейс взаимодействует с привязанным элементом управления изменением свойства в бизнес-объекте.</span><span class="sxs-lookup"><span data-stu-id="6ed22-106">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ed22-107">Пример</span><span class="sxs-lookup"><span data-stu-id="6ed22-107">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6ed22-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6ed22-108">See also</span></span>

- [<span data-ttu-id="6ed22-109">Практическое руководство. Применение шаблона PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="6ed22-109">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="6ed22-110">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ed22-110">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="6ed22-111">Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="6ed22-111">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="6ed22-112">Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ed22-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
