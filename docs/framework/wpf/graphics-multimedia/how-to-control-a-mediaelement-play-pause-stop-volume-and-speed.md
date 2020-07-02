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
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="db267-104">Практическое руководство. Управление элементом "MediaElement" (воспроизведение, пауза, остановка, громкость и скорость)</span><span class="sxs-lookup"><span data-stu-id="db267-104">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="db267-105">В следующем примере показано, как управлять воспроизведением мультимедиа с помощью <xref:System.Windows.Controls.MediaElement> .</span><span class="sxs-lookup"><span data-stu-id="db267-105">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="db267-106">В этом примере создается простой проигрыватель мультимедиа, позволяющий играть, приостанавливать, останавливать и пропускать назад и вперед, а также изменять соотношение громкости и скорости.</span><span class="sxs-lookup"><span data-stu-id="db267-106">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db267-107">Пример</span><span class="sxs-lookup"><span data-stu-id="db267-107">Example</span></span>  
 <span data-ttu-id="db267-108">Приведенный ниже код создает пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="db267-108">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db267-109"><xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>Свойство объекта <xref:System.Windows.Controls.MediaElement> должно быть установлено в значение, `Manual` чтобы иметь возможность интерактивно останавливать, приостанавливать и воспроизводить мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="db267-109">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="db267-110">Пример</span><span class="sxs-lookup"><span data-stu-id="db267-110">Example</span></span>  
 <span data-ttu-id="db267-111">Приведенный ниже код реализует функциональные возможности примеров элементов управления пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="db267-111">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="db267-112"><xref:System.Windows.Controls.MediaElement.Play%2A>Методы, <xref:System.Windows.Controls.MediaElement.Pause%2A> и <xref:System.Windows.Controls.MediaElement.Stop%2A> используются соответственно для воспроизведения, приостановки и остановки мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="db267-112">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="db267-113">Изменение <xref:System.Windows.Controls.MediaElement.Position%2A> свойства объекта <xref:System.Windows.Controls.MediaElement> позволяет пропускать его на носителе.</span><span class="sxs-lookup"><span data-stu-id="db267-113">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="db267-114">Наконец, <xref:System.Windows.Controls.MediaElement.Volume%2A> Свойства и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> используются для настройки громкости и скорости воспроизведения носителя.</span><span class="sxs-lookup"><span data-stu-id="db267-114">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="db267-115">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="db267-115">See also</span></span>

- [<span data-ttu-id="db267-116">Управление элементом MediaElement с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="db267-116">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
