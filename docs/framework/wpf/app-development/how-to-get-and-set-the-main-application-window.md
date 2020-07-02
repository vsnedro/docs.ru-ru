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
# <a name="how-to-get-and-set-the-main-application-window"></a>Как получить и задать основное окно приложения
В этом примере показано, как получить и задать основное окно приложения.  
  
## <a name="example"></a>Пример  
 Первый <xref:System.Windows.Window> экземпляр, созданный в приложении Windows Presentation Foundation (WPF), автоматически задается в <xref:System.Windows.Application> качестве главного окна приложения. <xref:System.Windows.Window>Скорее всего, это окно, указанное в качестве универсального идентификатора ресурса (URI) запуска (см <xref:System.Windows.Application.StartupUri%2A> .).  
  
 Первый <xref:System.Windows.Window> экземпляр можно также создать с помощью кода. Одним из примеров является открытие окна во время запуска приложения, как показано ниже:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 Иногда первый экземпляр на <xref:System.Windows.Window> самом деле не является главным окном приложения, например, экран-заставка. В этом случае можно указать основное окно приложения, используя разметку следующим образом:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Если главное окно указано автоматически или вручную, можно получить главное окно, <xref:System.Windows.Application.MainWindow%2A> используя следующий код, как в следующем примере:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
