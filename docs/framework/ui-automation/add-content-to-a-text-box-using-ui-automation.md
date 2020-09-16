---
title: Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса
description: См. Пример добавления содержимого в однострочное текстовое поле с помощью Microsoft UI Automation в .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 5e7ab77f1dcc2198e69255013eeb30cc703a235f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543138"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="19434-103">Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="19434-103">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="19434-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="19434-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="19434-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="19434-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="19434-106">Этот раздел содержит пример кода, демонстрирующий, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для вставки текста в однострочное текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="19434-106">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="19434-107">Альтернативный метод предоставляется для многострочных и многофункциональных элементов управления текстом, где [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] неприменимо.</span><span class="sxs-lookup"><span data-stu-id="19434-107">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="19434-108">Для сравнения в примере также демонстрируется использование методов Win32 для выполнения одинаковых результатов.</span><span class="sxs-lookup"><span data-stu-id="19434-108">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19434-109">Пример</span><span class="sxs-lookup"><span data-stu-id="19434-109">Example</span></span>  
 <span data-ttu-id="19434-110">В следующем примере выполняется пошаговая последовательность элементов управления текстом в целевом приложении.</span><span class="sxs-lookup"><span data-stu-id="19434-110">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="19434-111">Каждый элемент управления "текст" тестируется, чтобы определить, <xref:System.Windows.Automation.ValuePattern> можно ли получить объект из него с помощью <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="19434-111">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="19434-112">Если элемент управления "текст" поддерживает <xref:System.Windows.Automation.ValuePattern> , <xref:System.Windows.Automation.ValuePattern.SetValue%2A> метод используется для вставки пользовательской строки в элемент управления Text.</span><span class="sxs-lookup"><span data-stu-id="19434-112">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="19434-113">В противном случае <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> используется метод.</span><span class="sxs-lookup"><span data-stu-id="19434-113">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="19434-114">См. также</span><span class="sxs-lookup"><span data-stu-id="19434-114">See also</span></span>

- <span data-ttu-id="19434-115">[Пример вставки текста TextPattern](/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="19434-115">[TextPattern Insert Text Sample](/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>
