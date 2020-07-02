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
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="d2260-104">Практическое руководство. Управление элементом "MediaElement" с помощью объекта "Storyboard"</span><span class="sxs-lookup"><span data-stu-id="d2260-104">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="d2260-105">В этом примере показано, как управлять с помощью <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="d2260-105">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2260-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d2260-106">Example</span></span>  
 <span data-ttu-id="d2260-107">При использовании <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> для управления временем работы <xref:System.Windows.Controls.MediaElement> , функциональные возможности идентичны функциональным возможностям других <xref:System.Windows.Media.Animation.Timeline> объектов, таких как анимация.</span><span class="sxs-lookup"><span data-stu-id="d2260-107">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="d2260-108">Например, <xref:System.Windows.Media.MediaTimeline> компонент использует <xref:System.Windows.Media.Animation.Timeline> такие свойства, как <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> свойство, чтобы указать, когда следует запускать <xref:System.Windows.Controls.MediaElement> (запустить воспроизведение мультимедиа).</span><span class="sxs-lookup"><span data-stu-id="d2260-108">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="d2260-109">Он также использует <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство для указания времени <xref:System.Windows.Controls.MediaElement> активности (продолжительность воспроизведения мультимедиа).</span><span class="sxs-lookup"><span data-stu-id="d2260-109">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="d2260-110">Дополнительные сведения об использовании <xref:System.Windows.Media.Animation.Timeline> объектов с <xref:System.Windows.Media.Animation.Storyboard> см. в разделе [Общие сведения о раскадровках](storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d2260-110">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="d2260-111">В этом примере показано, как создать простой проигрыватель мультимедиа, который использует <xref:System.Windows.Media.MediaTimeline> для управления воспроизведением.</span><span class="sxs-lookup"><span data-stu-id="d2260-111">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="d2260-112">Проигрыватель мультимедиа содержит кнопки воспроизведения, паузы, возобновления и остановки.</span><span class="sxs-lookup"><span data-stu-id="d2260-112">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="d2260-113">Проигрыватель также имеет <xref:System.Windows.Controls.Slider> элемент управления, который выступает в качестве индикатора выполнения.</span><span class="sxs-lookup"><span data-stu-id="d2260-113">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="d2260-114">В следующем примере создается [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] для проигрывателя мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d2260-114">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="d2260-115">В следующем примере создаются функциональные возможности индикатора выполнения.</span><span class="sxs-lookup"><span data-stu-id="d2260-115">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d2260-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="d2260-116">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="d2260-117">Управление элементом MediaElement (воспроизведение, пауза, остановка, громкость и скорость)</span><span class="sxs-lookup"><span data-stu-id="d2260-117">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="d2260-118">Общие сведения о Storyboard</span><span class="sxs-lookup"><span data-stu-id="d2260-118">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="d2260-119">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="d2260-119">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d2260-120">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="d2260-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d2260-121">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="d2260-121">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="d2260-122">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d2260-122">Graphics and Multimedia</span></span>](index.md)
