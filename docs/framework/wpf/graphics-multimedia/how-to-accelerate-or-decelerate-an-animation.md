---
title: Практическое руководство. Ускорение или замедление анимации
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 7ab55ba44b866a992b9021284f170858f0108d15
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243015"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a>Как: Ускорить или замедлять анимацию

Этот пример показывает, как сделать анимацию ускоряться и замедляться с течением времени. В следующем примере несколько прямоугольников анимированы анимацией с различными <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> настройками и <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> настройками.  
  
## <a name="example"></a>Пример  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 Код был опущен из этого примера. Для полного кода [Animation Timing Behavior (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) см. [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic)
