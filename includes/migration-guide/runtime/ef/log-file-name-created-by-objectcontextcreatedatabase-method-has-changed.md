---
ms.openlocfilehash: e77e37156de759856c8a6f2e0c009caf9e1fe826
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496976"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>Имя файла журнала, созданного методом ObjectContext.CreateDatabase, изменилось в соответствии со спецификациями SQL Server

#### <a name="details"></a>Подробнее

При вызове метода <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> либо напрямую, либо с использованием Code First с поставщиком SqlClient и значения AttachDBFilename в строке подключения он создает файл журнала с именем filename_log.ldf вместо filename.ldf (где filename — имя файла, заданное значением AttachDBFilename). Это изменение улучшает отладку, предоставляя файл журнала, имя которого соответствует спецификациям SQL Server.

#### <a name="suggestion"></a>Предложение

Если имя файла журнала важно для приложения, приложение следует обновить для использования стандартного формата имени файла _log.ldf.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`

-->
