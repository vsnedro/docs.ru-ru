---
ms.openlocfilehash: 58dbb54d42d89b450134758072e3133ae4e6b13d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496249"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>Метод System.Threading.Tasks.Task больше не создает исключение ObjectDisposedException после удаления объекта

#### <a name="details"></a>Подробнее

За исключением <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle> методы <xref:System.Threading.Tasks.Task?displayProperty=fullName> больше не вызывают исключение <xref:System.ObjectDisposedException?displayProperty=fullName> после удаления объекта. Это изменение поддерживает использование кэшированных задач. Например, метод может возвратить кэшированную задачу для представления уже выполненной операции вместо выделения новой задачи. В предыдущих версиях платформы .NET Framework это было невозможно, поскольку любой потребитель задачи мог удалить ее, что делало ее непригодной для использования.

#### <a name="suggestion"></a>Предложение

Имейте в виду, что методы Task больше не могут создавать исключения <xref:System.ObjectDisposedException?displayProperty=fullName> при удалении объекта. Если приложение зависело от этого исключения, чтобы знать, что задача была удалена, его необходимо обновить, чтобы явно проверять состояние задачи с помощью <xref:System.Threading.Tasks.Task.Status>.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
