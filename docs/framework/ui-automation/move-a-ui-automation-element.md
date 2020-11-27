---
title: Перемещение элемента модели автоматизации пользовательского интерфейса
description: См. пример кода, демонстрирующий перемещение элемента модели автоматизации пользовательского интерфейса в указанное место на экране. В нем используются шаблоны элементов управления WindowPattern и Трансформпаттерн.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- moving elements
- elements, moving
- UI Automation, moving elements
ms.assetid: 4042cb44-e27e-4a03-ac36-9be1eed65b47
ms.openlocfilehash: 847015818a6c916beb5d026cb7f59a86cebd68cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261193"
---
# <a name="move-a-ui-automation-element"></a><span data-ttu-id="243ed-104">Перемещение элемента модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="243ed-104">Move a UI Automation Element</span></span>

> [!NOTE]
> <span data-ttu-id="243ed-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="243ed-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="243ed-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="243ed-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="243ed-107">В этом примере показано, как переместить элемент [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] в указанное место на экране.</span><span class="sxs-lookup"><span data-stu-id="243ed-107">This example demonstrates how to move a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element to a specified screen location.</span></span>  
  
## <a name="example"></a><span data-ttu-id="243ed-108">Пример</span><span class="sxs-lookup"><span data-stu-id="243ed-108">Example</span></span>  

 <span data-ttu-id="243ed-109">В следующем примере используются <xref:System.Windows.Automation.WindowPattern> <xref:System.Windows.Automation.TransformPattern> шаблоны элементов управления и для программного перемещения целевого приложения Win32 в дискретные расположения на экране и для трассировки <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent> .</span><span class="sxs-lookup"><span data-stu-id="243ed-109">The following example uses the <xref:System.Windows.Automation.WindowPattern> and <xref:System.Windows.Automation.TransformPattern> control patterns to programmatically move a Win32 target application to discrete screen locations and track the <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent>.</span></span>  
  
 [!code-csharp[WindowMove#1301](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1301)]
 [!code-vb[WindowMove#1301](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1301)]  
[!code-csharp[WindowMove#1300](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1300)]
[!code-vb[WindowMove#1300](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1300)]  
  
## <a name="see-also"></a><span data-ttu-id="243ed-110">См. также</span><span class="sxs-lookup"><span data-stu-id="243ed-110">See also</span></span>

- [<span data-ttu-id="243ed-111">Пример WindowPattern</span><span class="sxs-lookup"><span data-stu-id="243ed-111">WindowPattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/WindowMove)
