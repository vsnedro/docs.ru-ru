---
ms.openlocfilehash: 76425ca03c98cd6a23b8366257f9e0d53b486edb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497455"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Для совместного доступа к состоянию сеанса с Asp.Net StateServer все серверы на веб-ферме должны использовать одинаковую версию .NET Framework

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
