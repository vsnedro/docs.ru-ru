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
ms.openlocfilehash: d8fb67a84b7cba84fe65cd2f87baa6549122d2a2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276507"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a>Включение навигации в поставщике фрагментов автоматизации пользовательского интерфейса

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержится пример кода, демонстрирующий включение навигации в поставщике автоматизации пользовательского интерфейса для элемента, который находится в пределах фрагмента.  
  
## <a name="example"></a>Пример  

 В следующем примере кода реализуется метод <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> для элемента списка в списке. Родительский элемент является элементом списка, и одноуровневые элементы являются элементами в коллекции списка. Этот метод возвращает `null` (`Nothing` в Visual Basic) для направлений, которые не являются допустимыми; в данном случае <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> и <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, поскольку элемент не имеет дочерних элементов.  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о поставщиках автоматизации пользовательского интерфейса](ui-automation-providers-overview.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](server-side-ui-automation-provider-implementation.md)
