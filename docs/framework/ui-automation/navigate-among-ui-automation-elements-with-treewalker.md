---
title: Навигация между элементами автоматизированного пользовательского интерфейса с помощью TreeWalker
description: См. пример кода, в котором показано, как перемещаться между элементами модели автоматизации пользовательского интерфейса с помощью класса Тривалкер.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: e102e6ce258bef06d1fb44decfa1a3a27384e0bc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261219"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="2c7b2-103">Навигация между элементами автоматизированного пользовательского интерфейса с помощью TreeWalker</span><span class="sxs-lookup"><span data-stu-id="2c7b2-103">Navigate Among UI Automation Elements with TreeWalker</span></span>

> [!NOTE]
> <span data-ttu-id="2c7b2-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="2c7b2-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2c7b2-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="2c7b2-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="2c7b2-106">В этом разделе содержится пример кода, демонстрирующий навигацию между [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элементами с помощью <xref:System.Windows.Automation.TreeWalker> класса.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-106">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c7b2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2c7b2-107">Example</span></span>  

 <span data-ttu-id="2c7b2-108">В следующем примере используется <xref:System.Windows.Automation.TreeWalker.GetParent%2A> для прохода по [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] дереву до тех пор, пока не будет найден корневой элемент или Рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-108">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="2c7b2-109">Элемент, расположенный ниже, является родительским окном указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-109">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="2c7b2-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2c7b2-110">Example</span></span>  

 <span data-ttu-id="2c7b2-111">В следующем примере используется <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> и <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> для создания объекта <xref:System.Windows.Forms.TreeView> , который показывает все поддерево [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элементов, которые находятся в представлении элемента управления и включены.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-111">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="2c7b2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2c7b2-112">See also</span></span>

- [<span data-ttu-id="2c7b2-113">Получение элементов автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2c7b2-113">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
