---
title: Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса
description: Поиск и выделение текста с помощью автоматизации пользовательского интерфейса. В примере последовательно выполняется поиск и выделение каждого вхождения строки в содержимом элемента управления Text.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: e4aca4b5ccdbc429a3d6267afc09b9f8b99cd7e9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164194"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="d0a19-104">Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d0a19-104">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="d0a19-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="d0a19-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d0a19-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d0a19-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d0a19-107">В этом разделе показано, как последовательно искать и выделять каждое вхождение строки в содержимом элемента управления "текст" с помощью [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0a19-107">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0a19-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d0a19-108">Example</span></span>  
 <span data-ttu-id="d0a19-109">В следующем примере получается <xref:System.Windows.Automation.TextPattern> объект из текстового элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d0a19-109">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="d0a19-110"><xref:System.Windows.Automation.Text.TextPatternRange>Затем объект, представляющий текстовое содержимое всего документа, создается с помощью <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> свойства этого объекта <xref:System.Windows.Automation.TextPattern> .</span><span class="sxs-lookup"><span data-stu-id="d0a19-110">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="d0a19-111"><xref:System.Windows.Automation.Text.TextPatternRange>Затем создаются два дополнительных объекта для последовательного поиска и выделения.</span><span class="sxs-lookup"><span data-stu-id="d0a19-111">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="d0a19-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d0a19-112">See also</span></span>

- [<span data-ttu-id="d0a19-113">Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d0a19-113">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
