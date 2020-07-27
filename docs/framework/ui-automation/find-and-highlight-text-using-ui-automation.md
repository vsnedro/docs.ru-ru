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
# <a name="find-and-highlight-text-using-ui-automation"></a>Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе показано, как последовательно искать и выделять каждое вхождение строки в содержимом элемента управления "текст" с помощью [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .  
  
## <a name="example"></a>Пример  
 В следующем примере получается <xref:System.Windows.Automation.TextPattern> объект из текстового элемента управления. <xref:System.Windows.Automation.Text.TextPatternRange>Затем объект, представляющий текстовое содержимое всего документа, создается с помощью <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> свойства этого объекта <xref:System.Windows.Automation.TextPattern> . <xref:System.Windows.Automation.Text.TextPatternRange>Затем создаются два дополнительных объекта для последовательного поиска и выделения.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>См. также раздел

- [Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса](find-and-highlight-text-using-ui-automation.md)
