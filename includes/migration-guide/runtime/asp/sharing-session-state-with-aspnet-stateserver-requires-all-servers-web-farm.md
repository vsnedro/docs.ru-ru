---
ms.openlocfilehash: 0fe07ac21effacffc56d37ccb46a121f443acd20
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620172"
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

-<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
