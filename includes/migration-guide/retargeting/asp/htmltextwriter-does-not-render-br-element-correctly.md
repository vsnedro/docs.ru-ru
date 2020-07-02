---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615645"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a>HtmlTextWriter неправильно отображает элемент `<br/>`

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6, при вызове <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> и <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> с элементом `<BR />` правильно вставляется только один `<BR />` (вместо двух).

#### <a name="suggestion"></a>Предложение

Если приложение зависит от дополнительного тега `<BR />`, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> следует вызвать второй раз. Обратите внимание, что это изменение поведения влияет только на приложения, предназначенные для .NET Framework 4.6 или более поздних версий, поэтому другим вариантом является нацеливание на предыдущую версию платформы .NET Framework для получения старого поведения.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
