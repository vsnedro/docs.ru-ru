---
ms.openlocfilehash: 4d210eeedd2f228017634d29f11554deb6ed8079
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496115"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>Если в GridViews для свойства AllowCustomPaging установлено значение true, может возникать событие PageIndexChanging при выходе из последней страницы представления

#### <a name="details"></a>Подробнее

В результате ошибки в .NET Framework 4.5 иногда событие <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> не срабатывает для <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> со свойством <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework. Чтобы обойти эту проблему, приложение может иметь явный BindGrid в любом <code>Page_Load</code>, которое вызывает эти условия (<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> находится на последней странице, а Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> отличается от <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>). Кроме того, приложение можно изменить, чтобы разрешить разбивку на страницы (вместо пользовательского разбиения по страницам), поскольку в этом случае проблемы не возникают.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.UI.WebControls.GridView.AllowCustomPaging`

-->
