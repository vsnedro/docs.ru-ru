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
ms.openlocfilehash: e1784862433083f15d600ea2ec39aee2323bbd12
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168016"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>Навигация между элементами автоматизированного пользовательского интерфейса с помощью TreeWalker
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержится пример кода, демонстрирующий навигацию между [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элементами с помощью <xref:System.Windows.Automation.TreeWalker> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Automation.TreeWalker.GetParent%2A> для прохода по [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] дереву до тех пор, пока не будет найден корневой элемент или Рабочий стол. Элемент, расположенный ниже, является родительским окном указанного элемента.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> и <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> для создания объекта <xref:System.Windows.Forms.TreeView> , который показывает все поддерево [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элементов, которые находятся в представлении элемента управления и включены.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>См. также раздел

- [Получение элементов автоматизации пользовательского интерфейса](obtaining-ui-automation-elements.md)
