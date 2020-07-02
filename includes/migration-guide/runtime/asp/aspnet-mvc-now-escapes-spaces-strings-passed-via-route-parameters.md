---
ms.openlocfilehash: c53fe57f3278741a927a2f00b11af6e26dafce66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620148"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC теперь экранирует пробелы в строках, переданных через параметры маршрута

#### <a name="details"></a>Подробнее

Чтобы соответствовать стандарту RFC 2396, пробелы в путях маршрута теперь экранируются при заполнении параметров действий из маршрута. Таким образом, в то время как <code>/controller/action/some data</code> ранее соответствовал маршруту <code>/controller/action/{data}</code> и предоставлял <code>some data</code> в качестве параметра данных, теперь он будет предоставлять <code>some%20data</code>.

#### <a name="suggestion"></a>Предложение

Код должен быть обновлен для неэкранирования строковых параметров из маршрута. Если необходим исходный URI, доступ к нему можно получить с помощью API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5.2|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)></li></ul>|
