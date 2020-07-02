---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620183"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>Не следует использовать iPad в файле пользовательских возможностей, так как теперь это функция браузера

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.5 iPad является идентификатором в файле возможностей браузера ASP.NET по умолчанию, поэтому его не следует использовать в файле пользовательских возможностей

#### <a name="suggestion"></a>Предложение

Если требуются определенные возможности iPad, необходимо изменить поведение iPad, настроив возможности на предварительно определенном шлюзе refID &quot;IPad&quot; или создав новый идентификатор &quot;IPad&quot; путем сопоставления агента пользователя.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|
