---
title: Получение свойств элементов управления модели автоматизации пользовательского интерфейса
description: См. инструкции и пример, демонстрирующий получение текущих или кэшированных свойств элемента модели автоматизации пользовательского интерфейса.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 34a42355acce0beafbb9658baf6032e4e7e19fcb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276429"
---
# <a name="get-ui-automation-element-properties"></a>Получение свойств элементов управления модели автоматизации пользовательского интерфейса

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе показано, как получить свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента.  
  
### <a name="get-a-current-property-value"></a>Получение значения текущего свойства  
  
1. Получите объект, <xref:System.Windows.Automation.AutomationElement> свойство которого вы хотите получить.  
  
2. Вызовите <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> или извлеките <xref:System.Windows.Automation.AutomationElement.Current%2A> структуру свойства и получите значение от одного из его членов.  
  
### <a name="get-a-cached-property-value"></a>Получение значения кэшированного свойства  
  
1. Получите объект, <xref:System.Windows.Automation.AutomationElement> свойство которого вы хотите получить. Свойство должно быть указано в <xref:System.Windows.Automation.CacheRequest> .  
  
2. Вызовите <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> или извлеките <xref:System.Windows.Automation.AutomationElement.Cached%2A> структуру свойства и получите значение от одного из его членов.  
  
## <a name="example"></a>Пример  

 В следующем примере показаны различные способы получения текущих свойств <xref:System.Windows.Automation.AutomationElement> .  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>См. также

- [Свойства автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
- [Кэширование в клиентах автоматизации пользовательского интерфейса](caching-in-ui-automation-clients.md)
