---
title: Добавление и удаление элементов с помощью элемента управления ListView
description: Узнайте, как добавить или удалить элемент с Windows Forms элементом управления ListView, указав элемент и назначив ему свойства.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: db374ded69bcbd93527381d75a8ff751a1c9abe6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618094"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="cf015-103">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf015-103">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="cf015-104">Процесс добавления элемента в <xref:System.Windows.Forms.ListView> элемент управления Windows Forms состоит в основном из указания элемента и присвоения ему свойств.</span><span class="sxs-lookup"><span data-stu-id="cf015-104">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="cf015-105">Добавление или удаление элементов списка можно выполнить в любое время.</span><span class="sxs-lookup"><span data-stu-id="cf015-105">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="cf015-106">Добавление элементов программным способом</span><span class="sxs-lookup"><span data-stu-id="cf015-106">To add items programmatically</span></span>  
  
1. <span data-ttu-id="cf015-107">Используйте <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> метод <xref:System.Windows.Forms.ListView.Items%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="cf015-107">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="cf015-108">Удаление элементов программным способом</span><span class="sxs-lookup"><span data-stu-id="cf015-108">To remove items programmatically</span></span>  
  
1. <span data-ttu-id="cf015-109">Используйте <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> метод или <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> <xref:System.Windows.Forms.ListView.Items%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="cf015-109">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="cf015-110"><xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>Метод удаляет один элемент; <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> метод удаляет все элементы из списка.</span><span class="sxs-lookup"><span data-stu-id="cf015-110">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="cf015-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cf015-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="cf015-112">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="cf015-112">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="cf015-113">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="cf015-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
