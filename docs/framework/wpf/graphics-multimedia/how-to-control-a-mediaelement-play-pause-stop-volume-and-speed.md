---
title: Практическое руководство. Управление элементом "MediaElement" (воспроизведение, пауза, остановка, громкость и скорость)
description: Управление воспроизведением мультимедиа в Windows Presentation Foundation (WPF). Запуск, остановка, приостановка, переход назад и настройка громкости и скорости.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: da846299eaa1e36b6e5caab08bc1f861e9f9c46d
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853600"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Практическое руководство. Управление элементом "MediaElement" (воспроизведение, пауза, остановка, громкость и скорость)
В следующем примере показано, как управлять воспроизведением мультимедиа с помощью <xref:System.Windows.Controls.MediaElement> . В этом примере создается простой проигрыватель мультимедиа, позволяющий играть, приостанавливать, останавливать и пропускать назад и вперед, а также изменять соотношение громкости и скорости.  
  
## <a name="example"></a>Пример  
 Приведенный ниже код создает пользовательский интерфейс.  
  
> [!NOTE]
> <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>Свойство объекта <xref:System.Windows.Controls.MediaElement> должно быть установлено в значение, `Manual` чтобы иметь возможность интерактивно останавливать, приостанавливать и воспроизводить мультимедиа.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Пример  
 Приведенный ниже код реализует функциональные возможности примеров элементов управления пользовательского интерфейса. <xref:System.Windows.Controls.MediaElement.Play%2A>Методы, <xref:System.Windows.Controls.MediaElement.Pause%2A> и <xref:System.Windows.Controls.MediaElement.Stop%2A> используются соответственно для воспроизведения, приостановки и остановки мультимедиа. Изменение <xref:System.Windows.Controls.MediaElement.Position%2A> свойства объекта <xref:System.Windows.Controls.MediaElement> позволяет пропускать его на носителе. Наконец, <xref:System.Windows.Controls.MediaElement.Volume%2A> Свойства и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> используются для настройки громкости и скорости воспроизведения носителя.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Дополнительно

- [Управление элементом MediaElement с помощью раскадровки](how-to-control-a-mediaelement-by-using-a-storyboard.md)
