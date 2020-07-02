---
ms.openlocfilehash: 87cb2570d3d47a2acb85b5557141c0fef885516a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621820"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с `localhost`, завершается ошибкой

#### <a name="details"></a>Подробнее

В .NET Framework 4.6 и 4.6.1 попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с <code>localhost</code>, завершается ошибкой: &quot;При установлении подключения к SQL Server произошла ошибка сети или ошибка экземпляра. Сервер не найден или недоступен. Проверьте правильность имени экземпляра и настройку сервера SQL Server для удаленных подключений. (поставщик: сетевые интерфейсы SQL, ошибка: 26 — ошибка при обнаружении указанного сервера или экземпляра)&quot;

#### <a name="suggestion"></a>Предложение

Эта проблема устранена, и восстановлено прежнее поведение в .NET Framework 4.6.2. Для подключения к базе данных SQL Server, которой сопоставляется <code>localhost</code>, выполните обновление до .NET Framework 4.6.2.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6|
|Type|Среда выполнения|
