---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615658"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce поддерживает SHA-256 в приложениях, предназначенных для версии 4.0

#### <a name="details"></a>Подробнее

Раньше приложению ClickOnce с сертификатом, подписанным с SHA-256, требовалась платформа .NET Framework 4.5 или более поздней версии, даже если приложение предназначено для версии 4.0. Теперь приложения ClickOnce, предназначенные для .NET Framework 4.0, можно запускать на .NET Framework 4.0, даже если они подписаны с помощью алгоритма SHA-256.

#### <a name="suggestion"></a>Предложение

Это изменение удаляет зависимость и позволяет использовать сертификаты SHA-256 для подписи приложений ClickOnce на платформе .NET Framework 4 и более ранних версий.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6         |
| Type    | Изменение целевой платформы |
