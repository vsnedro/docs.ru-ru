---
title: Практическое руководство. Определение нажатия клавиши "Enter"
description: Обнаруживать нажатие клавиши ВВОД на клавиатуре в Windows Presentation Foundation. Этот пример состоит из XAML и файла кода программной части.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a955f52ec7bf93b32c70259b27fb51747664ac2e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163177"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Практическое руководство. Определение нажатия клавиши "Enter"
В этом примере показано, как определить, когда <xref:System.Windows.Input.Key.Enter> клавиша нажата на клавиатуре.  
  
 Этот пример состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла и файла кода программной части.  
  
## <a name="example"></a>Пример  
 Когда пользователь нажимает <xref:System.Windows.Input.Key.Enter> клавишу в <xref:System.Windows.Controls.TextBox> , входные данные в текстовом поле появляется в другой области [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .  
  
 Следующий код XAML создает пользовательский интерфейс, который состоит из <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Следующий программный код создает <xref:System.Windows.UIElement.KeyDown> обработчик событий.  Если нажата клавиша <xref:System.Windows.Input.Key.Enter> , появится сообщение в <xref:System.Windows.Controls.TextBlock> .  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о входных данных](input-overview.md)
- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
