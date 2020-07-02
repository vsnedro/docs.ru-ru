---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617547"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath создает исключение NullReferenceException

#### <a name="details"></a>Подробнее

В платформе .NET Framework 4.6.2 среда выполнения создает исключение `T:System.NullReferenceException` при получении значения `P:System.Web.HttpRuntime.AppDomainAppPath`, которое содержит нуль-символы. В .NET Framework 4.6.1 и более ранних версий среда выполнения создает исключение `T:System.ArgumentNullException`.

#### <a name="suggestion"></a>Предложение

В ответ на это изменение можно выполнить одно из следующих действий:

- обрабатывайте `T:System.NullReferenceException`, если приложение работает на платформе .NET Framework 4.6.2;
- обновите систему до версии .NET Framework 4.7, в которой восстановлено прежнее поведение, то есть создается исключение `T:System.ArgumentNullException`.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
