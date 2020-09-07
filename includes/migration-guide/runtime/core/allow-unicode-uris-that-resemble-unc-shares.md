---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496411"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Разрешение Юникода в URI, которые напоминают общие папки UNC

#### <a name="details"></a>Подробнее

В <xref:System.Uri?displayProperty=fullName> формирование URI файла, содержащего UNC-имя общей папки и символы Юникода, больше не приводит к созданию URI с недопустимым внутренним состоянием. Это поведение изменится, только если выполняются все указанные ниже условия:<ul><li>URI имеет схему <code>file:</code> и за ним следуют четыре или более косых черт;</li><li>имя узла начинается с символа подчеркивания или другого незарезервированного символа;</li><li>URI содержит символы Юникода.</li></ul>

#### <a name="suggestion"></a>Предложение

Приложения, работающие с URI, в обязательном порядке содержащими символы Юникода, потенциально могли использовать это поведение для запрета ссылок на общие папки UNC. Эти приложения должны использовать <xref:System.Uri.IsUnc>.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
