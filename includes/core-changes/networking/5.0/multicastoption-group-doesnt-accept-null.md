---
ms.openlocfilehash: 88a0b7e04c7015ca3fa5abd8a6897dafcbe41c49
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557973"
---
### <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a>MulticastOption.Group не принимает значение null

<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> больше не принимает значение `null`. Если задать для свойства значение `null`, вызывается исключение <xref:System.ArgumentNullException>.

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET для свойства <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> можно было задать значение `null`. Если впоследствии <xref:System.Net.Sockets.MulticastOption> передается в <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, среда выполнения вызывает исключение <xref:System.NullReferenceException>.

В .NET 5.0 и более поздних версиях исключение <xref:System.ArgumentNullException> вызывается, если для этого свойства задано значение `null`.

#### <a name="reason-for-change"></a>Причина изменения

Для соответствия рекомендациям по проектированию платформы свойство было обновлено для создания исключения <xref:System.ArgumentNullException>, если значение равно `null`.

#### <a name="recommended-action"></a>Рекомендованное действие

Убедитесь, что для <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> не задается значение `null`.

#### <a name="category"></a>Категория

Сети

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

-->
