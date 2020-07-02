---
ms.openlocfilehash: 39d609c955596354d1af28b4ed19d367dab0462b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620159"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>Событие Page.LoadComplete больше не заставляет элемент управления System.Web.UI.WebControls.EntityDataSource вызывать привязку данных

#### <a name="details"></a>Подробнее

Событие <xref:System.Web.UI.Page.LoadComplete> больше не заставляет элемент управления <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> вызывать привязку данных для изменений в параметрах создания/обновления/удаления. Это изменение исключает лишнее обращение к базе данных, не допускает сброса значений элементов управления и позволяет получить поведение, согласованное с другими элементами управления данными, такими как <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> и <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>. Это изменение дает другое поведение в том маловероятном случае, когда в приложении предполагается вызов привязки данных в событии <xref:System.Web.UI.Page.LoadComplete>.

#### <a name="suggestion"></a>Предложение

Если есть необходимость в привязке данных, вручную вызовите ее в событии, которое возникает раньше в обратной передаче.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|
