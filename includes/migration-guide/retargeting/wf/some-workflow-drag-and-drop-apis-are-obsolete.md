---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617291"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a>Некоторые API-интерфейсы перетаскивания в WorkFlow являются устаревшими

#### <a name="details"></a>Подробнее

Этот API перетаскивания рабочего процесса является устаревшим и будет вызывать предупреждения компилятора, если приложение перестроено на версии 4.5.

#### <a name="suggestion"></a>Предложение

Следует использовать новые API <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName>, которые поддерживают операции с несколькими объектами. Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версией компилятора. Интерфейсы API по-прежнему поддерживаются.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>
