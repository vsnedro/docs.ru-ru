---
title: Нахождение элемента автоматизации пользовательского интерфейса для элемента списка
description: См. пример, в котором показано, как найти элемент модели автоматизации пользовательского интерфейса для элемента списка, если известен индекс элемента.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: ec6464bc0ec504fd34ed113c9bed1a54a7d4eaec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168407"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="bc546-103">Нахождение элемента автоматизации пользовательского интерфейса для элемента списка</span><span class="sxs-lookup"><span data-stu-id="bc546-103">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="bc546-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="bc546-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bc546-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="bc546-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="bc546-106">В этом разделе показано, как получить <xref:System.Windows.Automation.AutomationElement> для элемента в списке, если известен индекс элемента.</span><span class="sxs-lookup"><span data-stu-id="bc546-106">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc546-107">Пример</span><span class="sxs-lookup"><span data-stu-id="bc546-107">Example</span></span>  
 <span data-ttu-id="bc546-108">В следующем примере показаны два способа извлечения указанного элемента из списка, один из которых использует <xref:System.Windows.Automation.TreeWalker> и другой с помощью <xref:System.Windows.Automation.AutomationElement.FindAll%2A> .</span><span class="sxs-lookup"><span data-stu-id="bc546-108">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="bc546-109">Первый способ, как правило, будет быстрее для элементов управления Win32, а второй — быстрее для элементов управления Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="bc546-109">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="bc546-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bc546-110">See also</span></span>

- [<span data-ttu-id="bc546-111">Получение элементов автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="bc546-111">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
