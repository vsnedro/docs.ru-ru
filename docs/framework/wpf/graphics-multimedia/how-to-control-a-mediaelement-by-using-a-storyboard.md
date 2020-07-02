---
title: Практическое руководство. Управление элементом "MediaElement" с помощью объекта "Storyboard"
description: Управление воспроизведением мультимедиа с помощью раскадровки в Windows Presentation Foundation (WPF). Рассмотрим этот пример для создания простого проигрывателя мультимедиа.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
ms.openlocfilehash: 5a5e41b9a28211495fd3374c1a51a655dd867bca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853732"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Практическое руководство. Управление элементом "MediaElement" с помощью объекта "Storyboard"
В этом примере показано, как управлять с помощью <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> .  
  
## <a name="example"></a>Пример  
 При использовании <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> для управления временем работы <xref:System.Windows.Controls.MediaElement> , функциональные возможности идентичны функциональным возможностям других <xref:System.Windows.Media.Animation.Timeline> объектов, таких как анимация. Например, <xref:System.Windows.Media.MediaTimeline> компонент использует <xref:System.Windows.Media.Animation.Timeline> такие свойства, как <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> свойство, чтобы указать, когда следует запускать <xref:System.Windows.Controls.MediaElement> (запустить воспроизведение мультимедиа). Он также использует <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство для указания времени <xref:System.Windows.Controls.MediaElement> активности (продолжительность воспроизведения мультимедиа). Дополнительные сведения об использовании <xref:System.Windows.Media.Animation.Timeline> объектов с <xref:System.Windows.Media.Animation.Storyboard> см. в разделе [Общие сведения о раскадровках](storyboards-overview.md).  
  
 В этом примере показано, как создать простой проигрыватель мультимедиа, который использует <xref:System.Windows.Media.MediaTimeline> для управления воспроизведением. Проигрыватель мультимедиа содержит кнопки воспроизведения, паузы, возобновления и остановки. Проигрыватель также имеет <xref:System.Windows.Controls.Slider> элемент управления, который выступает в качестве индикатора выполнения.  
  
 В следующем примере создается [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] для проигрывателя мультимедиа.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 В следующем примере создаются функциональные возможности индикатора выполнения.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>Дополнительно

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Управление элементом MediaElement (воспроизведение, пауза, остановка, громкость и скорость)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [Общие сведения о Storyboard](storyboards-overview.md)
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Практические руководства](audio-and-video-how-to-topics.md)
- [Графика и мультимедиа](index.md)
