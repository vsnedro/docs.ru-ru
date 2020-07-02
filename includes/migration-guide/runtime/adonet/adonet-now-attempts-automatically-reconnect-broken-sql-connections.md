---
ms.openlocfilehash: 23ba6064a283b47312a66f3636c2834a7d58106e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620184"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a>ADO.NET теперь пытается автоматически восстановить прерванное соединение SQL

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5.1 .NET Framework будет пытаться автоматически восстанавливать прерванные соединения SQL. Хотя это повысит надежность приложений, существуют крайние случаи, в которых приложению должно быть известно, что соединение было потеряно, чтобы можно было выполнить определенное действие после восстановления подключения.

#### <a name="suggestion"></a>Предложение

Если эта функция нежелательна из-за проблем совместимости, ее можно отключить, установив для свойства <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> строки соединения (или <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) значение 0.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5.1|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)></li></ul>|
