---
ms.openlocfilehash: 3eab96149be1e40d528cfd552bbe05ca766cf4e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620594"
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
