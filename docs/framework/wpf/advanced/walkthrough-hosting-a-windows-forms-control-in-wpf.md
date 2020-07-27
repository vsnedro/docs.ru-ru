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
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="edc4f-103">Пошаговое руководство. Размещение элементов управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="edc4f-103">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="edc4f-104">предоставляет множество элементов управления с богатым набором функций.</span><span class="sxs-lookup"><span data-stu-id="edc4f-104">provides many controls with a rich feature set.</span></span> <span data-ttu-id="edc4f-105">Однако иногда может потребоваться использовать элементы управления Windows Forms на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницах.</span><span class="sxs-lookup"><span data-stu-id="edc4f-105">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="edc4f-106">Например, у вас может быть существенный вклад в существующие элементы управления Windows Forms или имеется элемент управления Windows Forms, обеспечивающий уникальную функциональность.</span><span class="sxs-lookup"><span data-stu-id="edc4f-106">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>

<span data-ttu-id="edc4f-107">В этом пошаговом руководстве показано, как разместить <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> элемент управления Windows Forms на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] странице с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="edc4f-107">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="edc4f-108">Полный листинг кода задач, приведенных в этом пошаговом руководстве, см. в разделе [Пример размещения элемента управления Windows Forms в WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span><span class="sxs-lookup"><span data-stu-id="edc4f-108">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="edc4f-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="edc4f-109">Prerequisites</span></span>

<span data-ttu-id="edc4f-110">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="edc4f-110">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="edc4f-111">Размещение элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edc4f-111">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="edc4f-112">Чтобы разместить элемент управления MaskedTextBox, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="edc4f-112">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="edc4f-113">Создайте проект приложения WPF с именем `HostingWfInWpf` .</span><span class="sxs-lookup"><span data-stu-id="edc4f-113">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="edc4f-114">Добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="edc4f-114">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="edc4f-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="edc4f-115">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="edc4f-116">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="edc4f-116">System.Windows.Forms</span></span>

3. <span data-ttu-id="edc4f-117">Откройте файл MainWindow. XAML в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="edc4f-117">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="edc4f-118">Присвойте <xref:System.Windows.Controls.Grid> элементу имя `grid1` .</span><span class="sxs-lookup"><span data-stu-id="edc4f-118">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="edc4f-119">В представление конструирования или представлении XAML выберите <xref:System.Windows.Window> элемент.</span><span class="sxs-lookup"><span data-stu-id="edc4f-119">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="edc4f-120">В окно свойств перейдите на вкладку **события** .</span><span class="sxs-lookup"><span data-stu-id="edc4f-120">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="edc4f-121">Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событие.</span><span class="sxs-lookup"><span data-stu-id="edc4f-121">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="edc4f-122">Вставьте следующий код, чтобы обрабатывал <xref:System.Windows.FrameworkElement.Loaded> событие.</span><span class="sxs-lookup"><span data-stu-id="edc4f-122">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="edc4f-123">В верхней части файла добавьте следующий `Imports` `using` оператор или.</span><span class="sxs-lookup"><span data-stu-id="edc4f-123">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="edc4f-124">Нажмите клавишу **F5** для сборки и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="edc4f-124">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="edc4f-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="edc4f-125">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="edc4f-126">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="edc4f-126">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="edc4f-127">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="edc4f-127">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="edc4f-128">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="edc4f-128">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="edc4f-129">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edc4f-129">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="edc4f-130">Элементы управления Windows Forms и эквивалентные элементы управления WPF</span><span class="sxs-lookup"><span data-stu-id="edc4f-130">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="edc4f-131">Пример размещения элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="edc4f-131">Hosting a Windows Forms Control in WPF Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)
