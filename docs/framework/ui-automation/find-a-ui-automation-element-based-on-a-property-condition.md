---
title: Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства
description: Найти элемент модели автоматизации пользовательского интерфейса на основе условия для свойства. Нахождение элемента в дереве автоматизации пользовательского интерфейса на основе определенного свойства или свойств.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 5e5fa4fde9049bd87b2722fa9b7d084d96ff6f42
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168439"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержится пример кода, в котором показано, как можно наыскать элемент в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дереве на основе конкретного свойства или свойств.  
  
## <a name="example"></a>Пример  
 В следующем примере задается набор условий свойства, которые определяют определенный элемент (или элементы), представляющие интерес в <xref:System.Windows.Automation.AutomationElement> дереве. Затем выполняется поиск всех соответствующих элементов с помощью <xref:System.Windows.Automation.AutomationElement.FindAll%2A> метода, включающего ряд <xref:System.Windows.Automation.AndCondition> логических операций для ограничения количества совпадающих элементов.  
  
> [!NOTE]
> При поиске из необходимо <xref:System.Windows.Automation.AutomationElement.RootElement%2A> попытаться получить только прямые дочерние элементы. Поиск потомков может осуществлять итерацию сотен или даже тысяч элементов, что может привести к переполнению стека. Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>См. также раздел

- [Пример пункта меню InvokePattern и ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [Получение элементов автоматизации пользовательского интерфейса](obtaining-ui-automation-elements.md)
- [Использование свойства AutomationID](use-the-automationid-property.md)
