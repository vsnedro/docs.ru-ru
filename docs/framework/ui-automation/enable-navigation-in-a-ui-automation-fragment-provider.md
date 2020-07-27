---
title: Включение навигации в поставщике фрагментов автоматизации пользовательского интерфейса
description: Ознакомьтесь с примером, в котором показано, как включить навигацию в поставщике автоматизации пользовательского интерфейса для элемента, находящихся внутри фрагмента.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
ms.openlocfilehash: bf9e43e9d70b9191fba93e5efa4eae544196c735
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168484"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="d0c5c-103">Включение навигации в поставщике фрагментов автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d0c5c-103">Enable Navigation in a UI Automation Fragment Provider</span></span>
> [!NOTE]
> <span data-ttu-id="d0c5c-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d0c5c-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d0c5c-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d0c5c-106">В этом разделе содержится пример кода, демонстрирующий включение навигации в поставщике автоматизации пользовательского интерфейса для элемента, который находится в пределах фрагмента.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-106">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0c5c-107">Пример</span><span class="sxs-lookup"><span data-stu-id="d0c5c-107">Example</span></span>  
 <span data-ttu-id="d0c5c-108">В следующем примере кода реализуется метод <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> для элемента списка в списке.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-108">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="d0c5c-109">Родительский элемент является элементом списка, и одноуровневые элементы являются элементами в коллекции списка.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-109">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="d0c5c-110">Этот метод возвращает `null` (`Nothing` в Visual Basic) для направлений, которые не являются допустимыми; в данном случае <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> и <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, поскольку элемент не имеет дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-110">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="d0c5c-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d0c5c-111">See also</span></span>

- [<span data-ttu-id="d0c5c-112">Общие сведения о поставщиках автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d0c5c-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="d0c5c-113">Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="d0c5c-113">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
