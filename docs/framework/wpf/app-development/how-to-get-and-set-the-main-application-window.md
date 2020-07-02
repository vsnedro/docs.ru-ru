---
title: Как получить и задать основное окно приложения
description: Выполните приведенный ниже пример, чтобы получить и задать основное окно приложения в приложении Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 9bb5bce9b90482796acd8c62e77dc8bd9a850eeb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622683"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="d95b1-103">Как получить и задать основное окно приложения</span><span class="sxs-lookup"><span data-stu-id="d95b1-103">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="d95b1-104">В этом примере показано, как получить и задать основное окно приложения.</span><span class="sxs-lookup"><span data-stu-id="d95b1-104">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d95b1-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d95b1-105">Example</span></span>  
 <span data-ttu-id="d95b1-106">Первый <xref:System.Windows.Window> экземпляр, созданный в приложении Windows Presentation Foundation (WPF), автоматически задается в <xref:System.Windows.Application> качестве главного окна приложения.</span><span class="sxs-lookup"><span data-stu-id="d95b1-106">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="d95b1-107"><xref:System.Windows.Window>Скорее всего, это окно, указанное в качестве универсального идентификатора ресурса (URI) запуска (см <xref:System.Windows.Application.StartupUri%2A> .).</span><span class="sxs-lookup"><span data-stu-id="d95b1-107">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="d95b1-108">Первый <xref:System.Windows.Window> экземпляр можно также создать с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="d95b1-108">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="d95b1-109">Одним из примеров является открытие окна во время запуска приложения, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="d95b1-109">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="d95b1-110">Иногда первый экземпляр на <xref:System.Windows.Window> самом деле не является главным окном приложения, например, экран-заставка.</span><span class="sxs-lookup"><span data-stu-id="d95b1-110">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="d95b1-111">В этом случае можно указать основное окно приложения, используя разметку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d95b1-111">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="d95b1-112">Если главное окно указано автоматически или вручную, можно получить главное окно, <xref:System.Windows.Application.MainWindow%2A> используя следующий код, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d95b1-112">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
