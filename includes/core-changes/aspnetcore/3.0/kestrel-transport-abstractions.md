---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032806"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Kestrel. Удаление абстракций транспортировки и их преобразование в общедоступную версию

В рамках перехода от программного интерфейса типа "pubternal" API транспортного уровня Kestrel предоставляются в виде общедоступного интерфейса в библиотеке `Microsoft.AspNetCore.Connections.Abstractions`.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

- Абстракции, связанные с транспортировкой, были доступны в библиотеке `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`.
- Свойство `ListenOptions.NoDelay` было доступно.

#### <a name="new-behavior"></a>Новое поведение

- Интерфейс `IConnectionListener` появился в библиотеке `Microsoft.AspNetCore.Connections.Abstractions`, предоставляя наиболее используемые функции из библиотеки `...Transport.Abstractions`.
- Теперь `NoDelay` можно использовать в параметрах транспорта (`LibuvTransportOptions` и `SocketTransportOptions`).
- `SchedulingMode` использовать нельзя.

#### <a name="reason-for-change"></a>Причина изменения

Выполнение переноса ASP.NET Core 3.0 с pubternal API.

#### <a name="recommended-action"></a>Рекомендованное действие

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
