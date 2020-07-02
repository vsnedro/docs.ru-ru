---
ms.openlocfilehash: b2fcacdb02c411c4dcb12051bf0c6759faccdea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620666"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>Метод Replace в URL-адресах OData по умолчанию отключен

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5, метод Replace в URL-адресах OData по умолчанию отключен. Если метод Replace OData отключен (теперь по умолчанию), все запросы пользователя, включая функции Replace (которые используются редко), завершатся ошибкой.

#### <a name="suggestion"></a>Предложение

Если необходим метод Replace (который используется редко), его можно включить в параметрах конфигурации (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>). Однако включенный метод Replace может открывать уязвимости системы безопасности, поэтому он должен использоваться только после тщательной проверки.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
