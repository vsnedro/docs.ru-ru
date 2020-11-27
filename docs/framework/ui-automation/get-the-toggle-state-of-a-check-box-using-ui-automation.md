---
title: Получение состояния флажка с использованием автоматизации пользовательского интерфейса
description: См. пример кода, показывающий, как получить состояние переключения элемента управления (например, флажок) с помощью службы автоматизации пользовательского интерфейса Майкрософт.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, getting toggle states of check boxes
- check boxes, getting toggle states of
- getting, toggle states of check boxes
ms.assetid: 84fc31a3-175f-4e93-90a0-dd29d89b77ce
ms.openlocfilehash: 2ec0cc996461b13d0ddc3453188eeb3287a56be7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276442"
---
# <a name="get-the-toggle-state-of-a-check-box-using-ui-automation"></a>Получение состояния флажка с использованием автоматизации пользовательского интерфейса

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для получения состояния переключения элемента управления.  
  
## <a name="example"></a>Пример  

 В этом примере используется <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> метод <xref:System.Windows.Automation.AutomationElement> класса для получения <xref:System.Windows.Automation.TogglePattern> объекта из элемента управления и возврата его <xref:System.Windows.Automation.ToggleState> Свойства.  
  
 [!code-csharp[NavigatingWithTreeWalker#1200](../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigatingWithTreeWalker/CSharp/ClientClass.cs#1200)]
 [!code-vb[NavigatingWithTreeWalker#1200](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigatingWithTreeWalker/visualbasic/clientclass.vb#1200)]
