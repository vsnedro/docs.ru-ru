---
ms.openlocfilehash: d7a18a0b457c2a38f40c1da3b2f0bfc578259475
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621179"
---
### <a name="connection-pool-blocking-period-for-azure-sql-databases-is-removed"></a>Период блокировки пула соединений для баз данных Azure SQL удален

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6.2 в запросах на открытие подключения к известным базам данных Azure SQL (\*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de) удален период блокировки пула соединения, и ошибки открытия подключения не кэшируются. Почти сразу же после временных ошибок подключения будут выполняться повторные попытки запросов на открытие подключения. Это изменение позволяет немедленно повторять попытку открытого подключения к базам данных Azure SQL, повышая тем самым производительность облачных приложений. Для всех остальных попыток подключений период блокировки пула подключений продолжает действовать и далее.<p/>В .NET Framework 4.6.1 и более ранних версий, когда приложение обнаруживает временный сбой соединения при подключении к базе данных, невозможно быстро повторять попытки подключения, так как пул подключений кэширует ошибку и повторно создает ее в периоде от 5 секунд до 1 минуты. Дополнительные сведения см. в разделе [Пулы подключений SQL Server (ADO.NET)](~/docs/framework/data/adonet/sql-server-connection-pooling.md). Такое поведение является проблемным для подключений к базам данных Azure SQL, так как они часто завершаются временными ошибками, которые обычно устраняются через несколько секунд. Функция блокировки пула соединений означает, что приложение не может подключиться к базе данных в течение продолжительного периода, даже если база данных доступна и приложению необходимо преобразование в течение нескольких секунд.

#### <a name="suggestion"></a>Предложение

Если такое поведение нежелательно, вы можете настроить период блокирования пула подключений, задав свойство <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod?displayProperty=fullName>, представленное в .NET Framework 4.6.2. Значение этого свойства является членом перечисления <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=fullName>, которое принимает одно из трех значений:<ul><li><xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock></li><li><xref:System.Data.SqlClient.PoolBlockingPeriod.Auto></li><li><xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock></li></ul>Чтобы восстановить прежнее поведение, задайте свойству <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod?displayProperty=fullName> значение <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock>.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.2|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Data.Common.DbConnection.OpenAsync?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
