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
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="6e1ac-104">Практическое руководство. Определение нажатия клавиши "Enter"</span><span class="sxs-lookup"><span data-stu-id="6e1ac-104">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="6e1ac-105">В этом примере показано, как определить, когда <xref:System.Windows.Input.Key.Enter> клавиша нажата на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="6e1ac-105">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="6e1ac-106">Этот пример состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла и файла кода программной части.</span><span class="sxs-lookup"><span data-stu-id="6e1ac-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e1ac-107">Пример</span><span class="sxs-lookup"><span data-stu-id="6e1ac-107">Example</span></span>  
 <span data-ttu-id="6e1ac-108">Когда пользователь нажимает <xref:System.Windows.Input.Key.Enter> клавишу в <xref:System.Windows.Controls.TextBox> , входные данные в текстовом поле появляется в другой области [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e1ac-108">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="6e1ac-109">Следующий код XAML создает пользовательский интерфейс, который состоит из <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="6e1ac-109">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="6e1ac-110">Следующий программный код создает <xref:System.Windows.UIElement.KeyDown> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="6e1ac-110">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="6e1ac-111">Если нажата клавиша <xref:System.Windows.Input.Key.Enter> , появится сообщение в <xref:System.Windows.Controls.TextBlock> .</span><span class="sxs-lookup"><span data-stu-id="6e1ac-111">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="6e1ac-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6e1ac-112">See also</span></span>

- [<span data-ttu-id="6e1ac-113">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="6e1ac-113">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="6e1ac-114">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="6e1ac-114">Routed Events Overview</span></span>](routed-events-overview.md)
