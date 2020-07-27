---
title: Размещение элемента управления Windows Forms в WPF
description: Узнайте, как размещать элементы управления Windows Forms в Windows Presentation Foundation, которые уже предоставляют множество элементов управления с широким набором функций.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: ec67cf9fabaa5b7aadbb2a3c21ebf8dd828ee20f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164983"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>Пошаговое руководство. Размещение элементов управления Windows Forms в WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество элементов управления с богатым набором функций. Однако иногда может потребоваться использовать элементы управления Windows Forms на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницах. Например, у вас может быть существенный вклад в существующие элементы управления Windows Forms или имеется элемент управления Windows Forms, обеспечивающий уникальную функциональность.

В этом пошаговом руководстве показано, как разместить <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> элемент управления Windows Forms на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] странице с помощью кода.

Полный листинг кода задач, приведенных в этом пошаговом руководстве, см. в разделе [Пример размещения элемента управления Windows Forms в WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).

## <a name="prerequisites"></a>Предварительные требования

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.

## <a name="hosting-the-windows-forms-control"></a>Размещение элемента управления Windows Forms

### <a name="to-host-the-maskedtextbox-control"></a>Чтобы разместить элемент управления MaskedTextBox, выполните следующие действия.

1. Создайте проект приложения WPF с именем `HostingWfInWpf` .

2. Добавьте ссылки на следующие сборки.

    - WindowsFormsIntegration

    - System.Windows.Forms.

3. Откройте файл MainWindow. XAML в конструкторе WPF.

4. Присвойте <xref:System.Windows.Controls.Grid> элементу имя `grid1` .

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. В представление конструирования или представлении XAML выберите <xref:System.Windows.Window> элемент.

6. В окно свойств перейдите на вкладку **события** .

7. Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событие.

8. Вставьте следующий код, чтобы обрабатывал <xref:System.Windows.FrameworkElement.Loaded> событие.

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. В верхней части файла добавьте следующий `Imports` `using` оператор или.

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. Нажмите клавишу **F5** для сборки и запуска приложения.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Элементы управления Windows Forms и эквивалентные элементы управления WPF](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Пример размещения элемента управления Windows Forms в приложении WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)
