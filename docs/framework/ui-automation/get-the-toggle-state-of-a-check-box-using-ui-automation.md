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
ms.openlocfilehash: 36ec205a572fd6c9e52eec9d2c3e0618ddb0a07b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164145"
---
# <a name="get-the-toggle-state-of-a-check-box-using-ui-automation"></a>Получение состояния флажка с использованием автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для получения состояния переключения элемента управления.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> метод <xref:System.Windows.Automation.AutomationElement> класса для получения <xref:System.Windows.Automation.TogglePattern> объекта из элемента управления и возврата его <xref:System.Windows.Automation.ToggleState> Свойства.  
  
 [!code-csharp[NavigatingWithTreeWalker#1200](../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigatingWithTreeWalker/CSharp/ClientClass.cs#1200)]
 [!code-vb[NavigatingWithTreeWalker#1200](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigatingWithTreeWalker/visualbasic/clientclass.vb#1200)]
