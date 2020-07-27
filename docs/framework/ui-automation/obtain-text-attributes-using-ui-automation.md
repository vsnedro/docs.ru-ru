---
title: Получение атрибутов текста с помощью UI Automation
description: Узнайте, как получить текстовые атрибуты с помощью модели автоматизации пользовательского интерфейса. См. пример кода, который получает текстовые атрибуты из текстового диапазона.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
ms.openlocfilehash: b48f773e27088ba4b33ad01b299d77a0992a9159
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168003"
---
# <a name="obtain-text-attributes-using-ui-automation"></a>Получение атрибутов текста с помощью UI Automation
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для получения атрибутов текста из диапазона текста. Диапазон текста может соответствовать текущему расположению курсора (или пустому выделению) в документе, связанному выделению текста, коллекции разрозненных выделений текста или всему текстовому содержимому документа.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано получение <xref:System.Windows.Automation.TextPattern.FontNameAttribute> из диапазона текста.  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 Шаблон элемента управления <xref:System.Windows.Automation.TextPattern> в сочетании с классом <xref:System.Windows.Automation.Text.TextPatternRange> поддерживает базовые текстовые атрибуты, свойства и методы. Для функциональности элемента управления, не поддерживаемой <xref:System.Windows.Automation.TextPattern> или <xref:System.Windows.Automation.Text.TextPatternRange> , класс <xref:System.Windows.Automation.AutomationElement>предоставляет клиенту автоматизации пользовательского интерфейса методы для доступа к соответствующей собственной объектной модели.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о TextPattern модели автоматизации пользовательского интерфейса](ui-automation-textpattern-overview.md)
- [Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса](add-content-to-a-text-box-using-ui-automation.md)
- [Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса](find-and-highlight-text-using-ui-automation.md)
- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Получение сведений об атрибутах смешанного текста с помощью модели автоматизации пользовательского интерфейса](obtain-mixed-text-attribute-details-using-ui-automation.md)
