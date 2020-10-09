---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609142"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Для совместного доступа к состоянию сеанса с ASP.NET StateServer все серверы на веб-ферме должны использовать одинаковую версию .NET Framework

#### <a name="details"></a>Подробнее

При включении состояния сеанса <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> все серверы на данной веб-ферме должны использовать одинаковую версию платформы .NET Framework, чтобы состояние передавалось должным образом.

#### <a name="suggestion"></a>Предложение

Обновите версии платформы .NET Framework на веб-серверах, которые совместно и одновременно используют состояние.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
